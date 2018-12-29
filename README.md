![screenshot](https://github.com/fastrgv/RufasSlider/blob/master/nexus.jpg)


Click on the large tar.gz file under releases to download all source & binaries (both Mac & Linux), or use this link:

https://github.com/fastrgv/RufasSlider/releases/download/v2.8.8/rs5dec18.tar.gz

or for Windows users use this:
https://github.com/fastrgv/RufasSlider/releases/download/v2.8.8/rs5dec18tar.zip



# RufasSlider
## What's new:

**ver 2.8.8 -- 5dec18**

* Updated to SDL2 v2.0.8 (all 3 platforms);


**ver 2.8.7 -- 02sep18**

* Found & fixed problems with C++ auto solvers.
* Upgraded the C++ solvers to use improved splaytree code, and to use simpler and/or more robust search keys, including GMG and LinkRings.
* Now using SDL v207 uniformly in codes for all platforms.
* Removed Ada solvers;



See full revision history at end of this file


------------------------------------------------------------------
## RufasSlider Introduction

RufaSlider is a collection of 16 different block slider puzzles for kids and casual puzzlers that works on laptops and PCs running Windows, OSX or GNU/Linux.

It includes a Klotski-style family, a DirtyDozen family, and a Traffic-Rush family.  And now these puzzle families come with AutoSolvers to help you.

The Klotski family uses rectangles of 4 sizes: 1x1, 2x2, 1x2, 2x1. The objective in each game is stated near the window top, but usually involves moving a large block to a specified location within the window.  

The DirtyDozen family is similar except there are L-shaped puzzle pieces.

The Traffic-Rush family uses data, with 2x1, 1x2, 3x1, 1x3 rectangles. Here, the long rectangles represent cars or trucks that can only move [roll] lengthwise...the goal being to move the red car toward the shaded "exit door".

Note that a game description files are simple text files that allows users to define additional puzzles.

Several other classic block slider games are included:  Fifteen, Eight, Nine, Panama, MaBoy, GetMyGoat, 2-versions of HoleInOne, Suits, and 2-versions of LinkRings.  

To move a block, use the arrow keys. If the automatic block selector chooses the wrong block, simply click the cursor on the desired block before using the arrow key. Thusly, the games are laptop friendly.

Finally, there are autosolvers embedded into the TrafficRush, Klotski, DirtyDozen, LinkRings and Maboy games to be used interactively, using the (=)-key.  This provides an amazing tool to learn to solve seemingly hopeless problems.

--------------------------------------
## Features

* Works on PCs or laptops running Windows, OSX or GNU/Linux.  And if GNAT is installed you can build it yourself!  But first try the delivered, prebuilt binaries.
* Windows, GNU/Linux and OSX binaries provided, as well as full source.
* Laptop friendly controls;  supports Mac Retina displays.
* Uses SDL2;
* Uses SFML for applause sound;
* all runtime files are in ./data/
* all game data files are in ./puzzles/

----------------------------------------------


## Setup and Running:

Windows users see also "windows-setup.txt".  Mac users see "osx-setup.txt".


Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.

Windows users may see some error messages (that may be ignored) pertaining to directory links.  Directory links are needed only on OSX & Linux.


Open a command line terminal, then cd to the install directory.

Windows users type "winslid.bat" to begin puzzling.

Linux users should type "gnuslid.sh" to access any game.

Mac users may open a terminal, navigate to the install_directory, and type "macslid.sh" on the command line.


To move a block, use the arrow keys  (up),(dn),(lf),(rt);  If there is an ambiguity and the "automatic" selection mechanism chooses the wrong block to be moved, simply click on the desired block with the cursor before hitting a directional arrow.  At any time, hit the letter (r) to reset/restart, or (esc) to quit.  

For Rush, Bslider and DirtyDozen, you use the (n) key to go to the next puzzle, which in general is more difficult.  The (p) key takes you to the previous puzzle.

And for those times when a solution seems impossible, the more difficult puzzle families have an AutoSolver function using the (=)-key to step closer towards the solution:  rush, bslider, dirty12, maboy, and linkRings 

Please send questions, comments or corrections to

	fastrgv@gmail.com


----------------------------------------------

## Build Requirements:

 * a recent g++ compiler that supports -std=c++11, OR a GNAT-GPL Ada compiler from libre.adacore.com/download/ [that includes a nice g++ compiler]
 * graphics card that supports OpenGL version 3.3 or later;
 * Xcode g++ compiler, if using OSX;

-------------------------------------------------------

## Build Instructions:

-------------------------------------------------------
**Windows** => winAll.bat

build script that requires libraries included in ./libs/win/.

-------------------------------------------------------

**MacOSX** => osxAll.sh:

script for OSX that references [delivered] local copies of all nonstandard libraries in ./osxlibs/.  The intent is to allow anyone with Xcode and a g++ compiler on their Mac to build without having to install these nonstandard libraries.

------------------------------------------------------
**GNU/Linux** => gnuAll.sh:

utilizes semi-standard shared libraries that are delivered in this bundle under ./gnulibs/, along with the non-standard static libraries SDL2 & SFML.  This was used to build the executable, which should run in the presence of ./gnulibs/, whether or not your system already has those libraries.  The runtime loader will prefer system libraries if they are present.

If the delivered linux binary does not run, rebuild all using gnuAll.sh.  In case of problems, try installing gnat from Ada Libre because the g++ compiler that comes with it works fine.


### Fixable Link Problems during linux build:

On a linux build machine, you might have minor link errors, depending on its configuration.  If "libGL" cannot be found, this literally means "libGL.so" was absent.  But you might have "libGL.so.1" present.  In this case, simply create a softlink by changing to the libGL directory, then type the line:

sudo ln -s libGL.so.1 libGL.so  (and enter the admin password)

whence the linker should now be able to find what it wants.  But if there is more than one file libGL.so present on your system, make sure you use the best one;  i.e. the one that corresponds to your accelerated graphics.


----------------------------------------------

bfscmp.sh:
is a script that compiles any of the stand-alone solvers:  bfs, bfsr, bfsl, bfsLR on any platform.

-----------------------------------------------

In the unlikely event that the delivered **linux** binary does not run, AND recompilation fails to create a usable executable, try these...

-------------------------------------------------------
### Developers:  steps to compile and run on "other" linux distros.

* Install Cmake...complicated from source, easy using a system update.

* Install SDL2-dev.
	* First, try a system update of libSDL2-devel.
	* Downloading and building from source is the hardest way, but still easy.  Requires Cmake.

* Install SFML-dev.
	* First, try a system update of sfml-dev or libsfml-devel.  
	* Building from source using Cmake is difficult because there are several prerequisites, but if you add them one at a time based on the cmake error messages, it is achievable.

At this point, the delivered compile script is likely to work without mods.


## what is special about this project?
Uses the C++ programming language and fully modern OpenGL methods, with textures, shaders and uniforms.  Achieves version 3.3 core profile contexts.  Compiles and runs on Windows, GNU/Linux and Mac OSX systems.

Focusing on portability and open source freedom, this project relies on SDL2, a PNG-loader by Lode Vandevenne, and SFML-Audio (because of its elegant audio interface).





## Legal Mumbo Jumbo:

RufasSlider itself is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2017  <fastrgv@gmail.com>

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
tags:  kids, puzzle, rush-hour, klotski, slider

----------------------------------------------------------

## Best Download Site for all my games:
https://github.com/fastrgv?tab=repositories

====================================================

## Older Revision History

**ver 2.8.6 -- 12aug18**

* Enhanced linux portability by adding shared libs to distribution;
* Updated to SFML v2.5.0 & compile scripts to match;
* Fixed unreadable or misplaced text in linkRings, flat7, suits;
* Fixed auto solvers for dirty12 & maboy.
* Replaced autosolver for TrafficRush due to failure on Windows.

**ver 2.8.5 -- 02apr18**

* Corrected win-test & hooked up autosolver: GetMyGoat [gmg];
* Updated to lodepng 2018 [Lode Vandevenne];
* Improved & simplified OSX build system;
* Uninverted font file;


**ver 2.8.4 -- 24nov17**

* simplified Windows setup.
* improved key & mouse action.
* now windows recenter when changing size ( b-key or s-key ).
* upgraded to SDL v2.0.7 to solve a window focus problem.


**ver 2.8.3 -- 21nov17**

* Improved selection app to loop through puzzles rather than to use scripts to do that function.  Now the Mac Bundle execution does not terminate after a single puzzle.


**ver 2.8.2 -- 19nov17**

* modified Windows game system to hide executables, DLLs;
* improved build scripts;
* now properly handle paths with embedded spaces;


**ver 2.8.1 -- 12nov17**

* added scripting that restores the convenience of returning to the selection window without incurring escalating memory use.


**ver 2.8.0 -- 8nov17**

* added prebuilt executables for msWindows;
* added working build scripts for msWindows;
* linux binaries now put into ./bin/gnu/;
* refined initial sizing to fit laptop screens;
* improved code;  avoided memory leaks of prior releases;


**ver 2.7.8 -- 21oct17**

* Updated linux scripts to use a) SFML v2.4.2;  b) AdaCore 2017;
* Note that AdaCore 2017 works on OSX with no changes;
* Added startup messages listing OGL profile & version;
* Corrected relative paths to begin with ./ in scripts;
* Cleaned up various codes and libraries;


**v 2.7.7 - 17may17**

* Improved build scripts to enhance portability across different linux distributions.
* Executable names simplified now that OSX has its own directory.
* Enhanced functionality of flat7, flatAZ.
* Better help screens.
* Added missing gnu libs necessary to run on some linux hosts.


**v 2.7.6 - 30apr17**

* An entirely new app structure now allows playing multiple different puzzles without restarting, making it much easier to use.


**v 2.7.5 - 27apr17**

* Embedded AutoSolvers into rush, bslider, dirty12, maboy, and linkRings apps.  Simply press the "=" key to single step closer to the solution, regardless of current game state.  You can use the autosolvers to demonstrate how a complete solution is possible, or merely to give you a head start at getting out of a jam.  Thusly, many of these puzzles have become much friendlier for the casual puzzler.
* Improved messaging in linkRings puzzle.


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
* Mac OSX compilation uses static versions for all non-standard libraries.


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
* now, a single executable provides an entry point for all the puzzles.  This allows the user to point and click to start the puzzle of interest.  Use "rufas_osx" on Mac/OSX, or "rufas_gnu" on Gnu/Linux.

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

