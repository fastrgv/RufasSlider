![screenshot](https://github.com/fastrgv/RufasSlider/blob/master/nexus.jpg)


Click on the large tar.gz file under releases to download all source & binaries (both Mac & Linux), or use this link:

https://github.com/fastrgv/RufasSlider/releases/download/v2.7.4/rslid4jan17.tar.gz



# RufasSlider - v2.7.4
## What's new:

**v 2.7.4 - 4jan17**

* Updated to use new SFML libs.
* Improved sound code.
* Corrected a duplicate window glitch.
* Refined compiler scripts.


**v 2.7.3 - 30dec16**

* Updated linux compile scripts to use the gnat g++ compiler in case the gnu g++ compiler is absent.
* Added numerical block selector on the nine puzzle (nine.cc).
* Added option to show block letters in rush & bslider that match autosolver output solutions.
* Added 10 more traffic rush puzzles.
* Improved coding to elliminate hard constants and to support Intel Skylake embedded graphics.
* Improved linux build system to maximize distro-compatibility.


**v 2.7.2 - 14jul16**

* Added randomizer to flatAZ, flat7 so each run is different.
* Found and corrected a logic error in most slider games by defining and using a "same" function to determine nearness of two positions.


**v 2.7.1 - 12apr16**

* Revised linux compilation to use static versions of SDL2, SFML for enhanced portability.  Also added local library softlinks necessary for execution on some distros.
* Mac OS-X compilation uses static versions for all non-standard libraries.


**v 2.7 - 20feb16**

* added 11 more traffic-rush puzzles of my own design, for a total of 76.
* upgraded and simplified the architecture.  There is now only one executable.
* added a Mac binary bundle that acts much more like a typical Mac App.  This app is delivered in the installation directory, but could be moved elsewhere, such as your personal Applications directory.  Note that there are some soft [symbolic] links in the bundle that are resolved automatically when copied by the command "cp -r rufaslider.app destination-directory".
* added another puzzle solver, bfsl, that handles "MaBoy", "DirtyDozen", and any other block slider with L-shaped pieces.  So, now there are 3 solvers:  
	* bfs:  rectangular block solver.
	* bfsr: rush solver.
	* bfsl: L-shaped block solver.


**v 2.6 - 12feb16**

* added many traffic-rush puzzles.  Some are vertically oriented;  others are my own design using an experimental auto-generator.
* fixed some coding errors;  added guard, warning statements.
* generalized rush, bfsr to support vertically oriented puzzles.
* generalized and improved bfs, the bslider autosolver.
* upgraded filename sort within rush to be fully lexicographical.  The intent is to list the most difficult puzzles last.
* added minimum number of moves to rush objective statements.
* added DirtyDozen slider puzzles...12 increasingly difficult L-block sliders.
* and two autosolvers:
	* **bfs**:  only solves bslider
	* **bfsr**:  only solves rush.
* Note that the included autosolvers only work for "bslider" or "rush".  Solutions or hints for other puzzles might be found on Google, or at <http://www.jaapsch.net/puzzles/>.


**v 2.5 - 31jan16**

* added nine and hio4, a variation of hole-in-one, both Grabarchuk sliders.
* added my flat7 and flatAz sliders.


**v 2.4 - 30jan16**

* added "suits" slider puzzle (Grabarchuk) whose objective is to move all four suits one step clockwise.  (hint: same trick as panama).
* now, a single executable provides an entry point for all the puzzles.  This allows the user to point and click to start the puzzle of interest.  Use "rufas_osx" on Mac/OS-X, or "rufas_gnu" on Gnu/Linux.

**v 2.2 - 23aug15**

* improved bfs.cc (the automatic Breadth-First-Search block solver for slider) that writes the solution to a file named "path.txt".
 * created bfsr.cc solver for traffic rush puzzles that works similarly but writes the solution to a file named "rushpath.txt".
* Be aware that in the "slider" and "rush" executables, the block numbering is toggled using the (x) key to make it easy to follow the solution steps produced by the two solvers.
* improved responsiveness by reducing dlay from 0.3 to 0.1.

**v 2.1 - 1apr15**

* modified the call to SDL_Init so only required systems are initialized;
* improved the linux compile script and added comments to help it work properly;
* added full descriptions of minor edits that might be needed by an end user;


**v 2.0 - 28mar15**

* deleted unlinkRings;  instead simply type "linkRings i".  In fact any command line parameter will now initiate the inverse puzzle.


------------------------------------------------------------------
## RufasSlider Introduction

RufaSlider contains 16 different block slider puzzles including a Klotski-style family, a DirtyDozen family, and a Traffic-Rush family.

The Klotski family uses rectangles of 4 sizes: 1x1, 2x2, 1x2, 2x1. The objective in each game is stated near the window top, but usually involves moving a large block to a specified location within the window.

The Traffic-Rush family uses data, with 2x1, 1x2, 3x1, 1x3 rectangles. Here, the long rectangles represent cars or trucks that can only move [roll] lengthwise...the goal being to move the red car toward the "garage door" on the right.

Note that either game description file is a simple text file with a particular format that allows users to easily define additional puzzles.

Several other classic block slider games are included:  Fifteen, Eight, Nine, Panama, MaBoy, GetMyGoat, 2-versions of HoleInOne, Suits, DirtyDozen, and 2-versions of LinkRings.  There are also two solvers included called "bfs" (breadth-first-search), and "bfsr" that work for most bslider/rush puzzles.  It expects a puzzle file name as input, and outputs a text file with a list of moves indicated as a block number and direction.  Note that the (x)-key toggles the display of block numbers to enable following a solution generated by a solver.

To move a block, use the arrow keys. If the automatic block selector chooses the wrong block, simply click the cursor on the desired block before using the arrow key. Thusly, the games are laptop friendly.

Works on Macs running OS-X and PCs running GNU/Linux.

--------------------------------------
## Features

 * Uses SDL2;
 * Works on OS-X Retina displays;
 * Uses SFML for applause sound;
 * all runtime files are in ./data/
 * all game data files are in ./puzzles/

----------------------------------------------

## Build Requirements:

 * a recent gcc compiler that supports -std=c++11;
 * graphics card that supports OpenGL version 3.3 or later;

-------------------------------------------------------

## Build Instructions:
**MacOSX** => ocmp.sh:

script for OSX that references [delivered] local copies of all nonstandard libraries in ./osxlibs/.  The intent is to allow anyone with a c++ compiler on their Mac to build without having to install these nonstandard libraries.

------------------------------------------------------
**GNU/Linux** => scmp.sh

utilizes semi-standard shared libraries that are delivered in this bundle under ./gnulibs/, along with the non-standard static libraries SDL2 & SFML.  This was used to build the executable, which should run in the presence of ./gnulibs/, whether or not your system already has those libraries.  The runtime loader will prefer system libraries if they are present.

If the delivered linux binary does not run, rebuild using scmp.sh.


### Minor Link Problems during linux build:

On a linux build machine, you might have minor link errors, depending on its configuration.  If "libGL" cannot be found, this literally means "libGL.so" was absent.  But you might have "libGL.so.1" present.  In this case, simply create a softlink by changing to the libGL directory, then type the line:

sudo ln -s libGL.so.1 libGL.so  (and enter the admin password)

whence the linker should now be able to find what it wants.  But if there is more than one file libGL.so present on your system, make sure you use the best one;  i.e. the one that uses your accelerated graphics.




----------------------------------------------

bfscmp.sh:
is a script that compiles either bfs or bfsr or bfsl on any platform.

-----------------------------------------------

In the unlikely event that the delivered **linux** binary does not run, and recompilation fails to create a usable executable, try these...

-------------------------------------------------------
### Steps to compile and run on "other" linux distros.

* Install Cmake...complicated from source, easy using a system update.

* Install SDL2-dev.
	* First, try a system update of libSDL2-devel.
	* Downloading and building from source is the hardest way, but still easy.  Requires Cmake.

* Install SFML-dev.
	* First, try a system update of sfml-dev or libsfml-devel.  
	* Building from source using Cmake is difficult because there are several prerequisites, but if you add them one at a time based on the cmake error messages, it is achievable.

At this point, the delivered compile script is likely to work without mods.



## Running:

Unzip the archive and you will see a new directory appear with a name like bundle+date", that you should rename to something like install_directory.  

Linux users should then cd to install_directory, then, at the command line, type "rufaslider_gnu" to access any game.  You may also double click its icon in file manager.

Mac users note that this game may be initiated in two ways.  First, by opening a terminal, navigating to the install_directory, and typing "rufaslider_osx" on the command line.   Second by navigating to the installation directory in Finder and clicking the "rufaslider.app" icon named "rufaslider".
 

The install_directory should contain subdirectories named "data", "libLocal", "incLocal", "puzzles".

To move a block, use the arrow keys  (up),(dn),(lf),(rt);  If there is an ambiguity and the "automatic" selection mechanism chooses the wrong block to be moved, simply click on the desired block with the cursor before hitting a directional arrow.  At any time, hit the letter (r) to reset/restart, or (esc) to quit.  

For Rush, Bslider and DirtyDozen, you use the (n) key to go to the next puzzle, which in general is more difficult.  The (p) key takes you to the previous puzzle.

Remember that (x) toggles block letters that allow you to follow solution instructions from one of the autosolvers.


Please send questions, comments or corrections to

	fastrgv@gmail.com

## Legal Mumbo Jumbo:

RufasSlider itself is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2016  <fastrgv@gmail.com>

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.

 You may read the full text of the GNU General Public License
 at <http://www.gnu.org/licenses/>.

----------------------------------------------------------

## Media Files for RufasSlider:

### General Note
The particular choice of sound file delivered is not essential to the function of the game and is easily replaced.  This software is primarily intended as a tutorial example of modern OpenGL methods.  The only requirements are that sounds be in WAV format.

### SoundFile (small-applause.wav)
...are from freesound.org and is covered by the Creative Commons Attribution noncommercial license documented in the accompanying file creativeCommons.txt.   See "small-applause.txt" for details and URL.


### ImageFiles (x.png)
...for text-textures were created using gimp and are also covered by the GNU GPL v3 license.  Thanks to unluckystudio.com [Sujit Kumar Yadav] for car sprites, whose colors I modified slightly with GIMP, and to OpenGameArt.org for the playing card symbols under a cc-by-3.0 license (see http://creativecommons.org/) uploaded there by IronStarMedia.co.uk


### LodePNG (png loader module: lodepng.cpp lodepng.h)
are files copyrighted by Lode Vandevenne and so marked with all the details of their permitted uses near the tops of those two files.

### Other Credits and Thanks:
Serhiy Grabarchuk and Peter Grabarchuk for their "Hole in One", "Hole in One plus 4", "Nine", and "Four Suits" puzzles.

----------------------------------------------------------

## Best Download Site for all my games:
https://github.com/fastrgv?tab=repositories


