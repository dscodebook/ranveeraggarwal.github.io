---
layout: post
title: "Installing GLFW on Ubuntu"
categories: tutorials
tyf: Tutorial
---
 
GLFW is a lightweight utility library for use with OpenGL. It provides programmers with the ability to create and manage windows and OpenGL contexts, as well as receive input from joystick, keyboard, mouse, time and clipboard. 
For my graphics course, I wanted to install it on my system, but thanks to the complicated instructions and a small bug in the release that wasn't gonna happen easily.

---
##The Issue (Don't do this)
So, the instructions given on the website tells you get inside the downloaded folder after unzipping it do the following:

    cmake .
    make
    make install
    
Doing this and running your OpenGL program gives the following error:

    usr/bin/ld: cannot find -lglfw

This is because the defaut release doesn't make a shared library.

---
##What to do?

1. Delete your unzipped folder (if you unzipped it)
2. Extract it again, preferably in the folder `/usr/local`
3. Open it and open the file `CMakeLists.txt` in any editor (if your file is in `/usr/local`, you might need `sudo`)
4. Look for build `options`. Change
5. 
        option(BUILD_SHARED_LIBS "Build shared libraries" OFF)

    to
    
        option(BUILD_SHARED_LIBS "Build shared libraries" ON)
        
    and save
5. Now do the following (same as above):

        cmake .
        make
        make install
        
    Use root if your folder was in `/usr/local`
6. Lastly, run `ldconfig`. You can do this by 
        
        sudo ldconfig

And now your GLFW is successfully installed.
