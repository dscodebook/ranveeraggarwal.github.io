---
layout: project
categories: projects
title: "Lightcuts"
---

Here we have implemented Lightcuts: A scalable approach to illumination by Bruce Walter, Sebastian Fernandez, Adam Arbree, Kavita Bala, Mike Donikian, Don Greenberg, presented at Siggraph 2015.  
Lightcuts is a scalable framework for computing realistic illumination. It handles arbitrary geometry, non-diffuse materials, and illumination from a wide variety of sources including point lights, area lights, HDR environment maps, sun/sky models, and indirect illumination. At its core is a new algorithm for accurately approximating illumination from many point lights with a strongly sublinear cost. We show how a group of lights can be cheaply approximated while bounding the maximum approximation error. A binary light tree and perceptual metric are then used to adaptively partition the lights into groups to control the error vs. cost tradeoff. 