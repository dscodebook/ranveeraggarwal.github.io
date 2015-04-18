---
layout: project
categories: projects
title: "Lightcuts"
tyf: Project
comments: true
---

Abhinav Gupta    
Ranveer Aggarwal

##Introduction
Here we have implemented Lightcuts: A scalable approach to illumination by Bruce Walter, Sebastian Fernandez, Adam Arbree, Kavita Bala, Mike Donikian, Don Greenberg, presented at Siggraph 2005.    

Lightcuts is a scalable framework for computing realistic illumination. It handles arbitrary geometry, non-diffuse materials, and illumination from a wide variety of sources including point lights, area lights, HDR environment maps, sun/sky models, and indirect illumination. At its core is a new algorithm for accurately approximating illumination from many point lights with a strongly sublinear cost. We show how a group of lights can be cheaply approximated while bounding the maximum approximation error. A binary light tree and perceptual metric are then used to adaptively partition the lights into groups to control the error vs. cost tradeoff.

The link for the paper is: http://www.cs.cornell.edu/~kb/projects/lightcuts/  

##Implementation
We have modified the source code of pbrt-v2, which we have forked from https://github.com/mmp/pbrt-v2.
In our implementation we consider point light sources and diffuse surfaces only, the goal being to compare the render times between Vanilla PBRT and our Lightcuts implementation.

##Installation
After cloning this repository or downloading the source code, run
	
	make

in the src/ folder and generate the binaries.

##Running
In the root directory, run

	./src/bin/pbrt scenes/<filename>

The image will be generated in a file called &lt;filename&gt;.exr

##Behind the Scenes
We implemented our own light node data structure. The data structure consists of the following:
* Pointer to the representative light
* Total intensity of the cluster
* Bounding Box Coordinates
* Pointers to children
* A flag whether the node is a leaf

Next, we build the light tree bottom up. Initially, all nodes are leaf nodes and represent individual lights of the scene. Then, we create a 2 dimensional cost matrix, and store the bounding box diagonal lengths multiplied by the sum of intensities between every two nodes. This metric decides whether two nodes get clustered or not. We then find the minimum cost and cluster the two respective nodes. Next, we update the cost matrix using the new light node formed out of the two child nodes and repeat the same process until we are left with just one node. This one node represents the root of the light tree.

We construct the light tree in src/core/scene.cpp

When computing the direct illumination at a point, we choose that clustering of lights which produces error less than an acceptable threshold. We do this by starting with a coarse lightcut (consisting only of the root) and refining the lightcut by splitting the node with the maximum error. The error is bounded by the maximum possible value of the illumination. This involves calculating upper bounds on the Geometric, Material and Visibility terms in the rendering equation.

	Illumination = Material Term * Geometric Term * Visibility Term * Intensity

The Geometric term is bounded by the inverse of the minimum squared distance between the bounding box and the point to be illuminated.

The Material term is the upper bound on the BRDF (which is constant for Lambertian surfaces) multiplied by the upper bound on the cosine of the angle between surface normal and the direction of light. This is estimated by aligning the normal to the z-axis (by computing a rotation or a reflection matrix). Then, the point with the maximum z-coordinate and minimum absolute x and y coordinates is selected in the bounding box.

The Visibility term is trivially bounded by 1.

We changed the UniformSampleAllLights and the EstimateDirect functions in PBRT’s src/core/integrator.cpp file for error computation and lightcut selection.

We wrote a Python script to generate random light sources and used them to compare the time taken while rendering using Vanilla PBRT and our implementation.

##Results
We ran both non-lightcut and lightcut version for 200 and 1000 lights placed randomly in a 100x100x100 cube in the scene. Here are the results.
<table class="table">
	<tr>
		<td><b>Light sources</b></td>
		<td><b>Vanilla PBRT</b></td>
		<td><b>Lightcuts Implementation</b></td>
	</tr>
	<tr>
		<td>1000</td>
		<td>
			real	34m36.050s    
			user	255m57.447s    
			sys		0m6.578s   
		</td>
		<td>
			real	29m2.530s    
			user	168m41.736s    
			sys		0m6.004s    
		</td>
	</tr>
</table>

Here are the generated images:
<table class="table">
	<tr>
		<td><b>Light sources</b></td>
		<td><b>Vanilla PBRT</b></td>
		<td><b>Lightcuts Implementation</b></td>
	</tr>
	<tr>
		<td>
			1000
		</td>
		<td>
			<img class="img-responsive" src="/assets/images/projects/lightcuts/l1000.jpg">
		</td>
		<td>
			<img class="img-responsive" src="/assets/images/projects/lightcuts/l1000.jpg">
		</td>
	</tr>
</table>

##Conclusion
So, as we see, as the number of light sources increase, the time to render decreases. This is because now, instead of having to contribute illumination from all light sources, the program has to compute illumination only from a few representative light sources, thereby reducing the amount of computation required.