![screenshot](https://github.com/fastrgv/RufasSlider/blob/master/nexus.jpg)


Click on the large tar.gz file under releases to download all source & binaries (both Mac & Linux), or use this link:

https://github.com/fastrgv/RufasSlider/releases/download/v3.3.2/rs7nov22.7z

Type "7z x filename.7z" to extract the archive.

## GitHub downloaders Note: Please ignore the "Source code" zip & tar.gz files. (They are auto-generated by GitHub). Click on the large 7z file under releases to download all source & binaries (Windows,Mac & Linux). Then, type "7z x filename" to extract the archive. 










# RufasSlider

## What's new:


**ver 3.3.2 -- 07nov22**

* Improved robustness of auto-solvers.
* Added "live" embedded solver for annoying sliders puzzles.
* Added external solver "bfsa" for Annoying sliders that also solves Klotski-class, DirtyDozen, & TrafficRush puzzle files.
* Revised compilation scripts to hide object files.


**ver 3.3.1 -- 22oct22**

* Corrected direction of traffic-rush red car.
* Added 2 Quzzle puzzles to the Klotski app.
* Added 16 Annoying Sliders...that look small but are not easy.


**ver 3.3.0 -- 01oct22**

* Now using simpler-to-setup GNU g++ for Win64.
* Now make game subwindow grab focus upon opening.


**ver 3.2.4 -- 16sep22**

* Now using GNU g++ rather than defunct AdaCore g++ compiler.


See full revision history at end of this file


------------------------------------------------------------------
## RufasSlider Introduction

RufaSlider is a collection of 16 different block slider puzzles for kids and casual puzzlers that works on laptops and PCs running Windows, OSX or most Linux distros.

It includes a Klotski-style family, a DirtyDozen family, and a Traffic-Rush family.  And now these puzzle families come with AutoSolvers to help you.

The Klotski family uses rectangles of 4 sizes: 1x1, 2x2, 1x2, 2x1. The objective in each game is stated near the window top, but usually involves moving a large block to a specified location within the window.  

The DirtyDozen family is similar except there are L-shaped puzzle pieces.

The Traffic-Rush family uses cars or trucks that can only move [roll] lengthwise...the goal being to move the red car toward the shaded "exit door".

The game description files are simple text files that allow users to define additional puzzles.

Several other classic block slider games are included:  Fifteen, Eight, Nine, Panama, MaBoy, GetMyGoat, 2-versions of HoleInOne, Suits, and 2-versions of LinkRings. 

* Also included are two of my own creations: Flat7, FlatAZ. These are 2-dimensional versions of my 3D "Rufas Cubes", available at:  https://sourceforge.net/projects/rufascube/

* Many of these puzzles are also available as retro ASCII puzzles that run in a command-line terminal on Windows, OS-X and Gnu/Linux; and is available at: https://sourceforge.net/projects/coterminalapps/

* These are all 2D slider puzzles. I created four 3D slider puzzles that also run on Windows, OS-X, and Linux, using OpenGL graphics. It is available at: https://sourceforge.net/projects/reliquarium/

To move a block, use the arrow keys. If the automatic block selector chooses the wrong block, simply click the cursor on the desired block before using the arrow key. Thusly, the games are laptop friendly.

Rush & maboy allow mouse drags to initiate the moves.

Finally, there are autosolvers embedded into the TrafficRush, Klotski, DirtyDozen, LinkRings and Maboy games to be used interactively, using the (=)-key.  This provides an amazing tool to learn to solve seemingly hopeless problems.

FTTB, Annoy has no built-in solver, but the solutions are colocated with the input files under ./puzzles/. EG, for Annoying#16, input: ad16.blk; soln: ad16soln.txt. Note that you should turn on the alphabetic block symbols before trying to use a solution file.

--------------------------------------
## Features

* Works on PCs or laptops running Windows, OSX(>=10.13) or GNU/Linux.  And if GNAT is installed you can build it yourself!  But first try the delivered, prebuilt binaries.
* Windows, GNU/Linux and OSX binaries provided, as well as full source.
* Laptop friendly controls; can support Mac Retina displays.
* Uses SDL2;
* Uses OpenAL-audio for sound.
* all runtime files are in ./data/
* all game data files are in ./puzzles/

* no installation
* no dependencies
* simply unzip in your Downloads directory, and run;
* or unzip onto a USB flash drive [w/same file format] and run.

----------------------------------------------


## Setup and Running:

Windows users see also "windows-setup.txt".
Mac users see "osx-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.
Open a command line terminal, then cd to the install directory.

----------------------------------------------------------------
Windows users type "winslid.bat" to begin puzzling.
You may also cd ./bin/w64/, and then type any individual puzzle name, eg: rush.exe.

----------------------------------------------------------------
Linux users should type "gnuslid.sh" to access any game.
You may also ce ./bin/gnu/, and then type any individual puzzle name, eg: rush.

Also, if you have wine installed on your linux system, you can run the windows EXE thusly:

	* cd bin/w64/
	* wine rufaslid.exe


----------------------------------------------------------------
Mac users may open a terminal, navigate to the install directory, and type "macslid.sh" on the command line.  Alternatively, Mac users may initiate the game in the usual way by navigating to the installation directory in Finder and clicking the "rufaslider.app" icon named "rufaslider".

In many puzzles, a mouse drag can initiate a block move.  However, the preferred method to move a block is to select it using a mouse click, then use the arrow keys  (up),(dn),(lf),(rt).  The block selection is not necessary when only one block can move in the indicated direction. EG FourSuits, eight & fifteen never require block selection since there is only 1 empty space.

At any time, hit the letter (r) to reset/restart, or (esc) to quit.  

For Rush, Bslider, Annoying and DirtyDozen, you use the (n) key to go to the next puzzle, which in general is more difficult.  The (p) key takes you to the previous puzzle.

Note that I created about 20% of the Rush puzzles (filenames that end "my.rush"), including the most difficult one "zzzz_89my.rush".


And for those times when a solution seems impossible, the more difficult puzzle families have an AutoSolver function using the (=)-key to step closer towards the solution:  rush, bslider, dirty12, maboy, annoy, and linkRings.  Remember that you can stop using the autosolver at any time and try to manually solve the puzzle from a configuration that is a few steps closer to a solution.

Note that there are two "external" solvers available:  1) fbfsr for traffic rush puzzles (writes to rpath.txt);  2) fbfsl (writes to lpath.txt) for a) MaBoy; b) dirtyDozen; c) bslider puzzles.  Simply type the executable name followed by the puzzle file name.  For example to solve the second DirtyDozen puzzle type "fbfsl ../../puzzles/dd02.blk".  The solution is written to a file in the current directory, in this case, named lpath.txt.  Then, to follow the output instructions, start the puzzle and reveal the letters by hitting the (a)-key.

Please send questions, comments, corrections or improvements to

	fastrgv@gmail.com


----------------------------------------------

## Build Requirements:

 * a recent GNU g++ compiler that supports -std=c++11.
 * graphics card that supports OpenGL version 3.3 or later;

-------------------------------------------------------

## Build Instructions:

Begin by installing GNU g++.

-------------------------------------------------------
**Windows64** => w64all.bat

Windows developers, please also read "gnuOnWindows.txt".

-------------------------------------------------------

**MacOSX** => osxAll.sh:

script for OSX that references [delivered] local copies of all nonstandard libraries in ./libs/osx/.  The intent is to allow anyone to build without having to install these nonstandard libraries.

------------------------------------------------------
**GNU/Linux** => gnuAll.sh:

utilizes shared libraries that are delivered in this bundle under ./libs/gnu/.  These were used to build the executable, which should run in the presence of ./libs/gnu/, whether or not your system already has those libraries.  The runtime loader will prefer system libraries if they are present.

If the delivered linux binary does not run, rebuild all using gnuAll.sh.  In case of problems.


### Fixable Link Problems during linux build:

On a linux build machine, you might have minor link errors, depending on its configuration.  If "libGL" cannot be found, this literally means "libGL.so" was absent.  But you might have "libGL.so.1" present.  In this case, simply create a softlink by changing to the libGL directory, then type the line:

sudo ln -s libGL.so.1 libGL.so  (and enter the admin password)

whence the linker should now be able to find what it wants.  But if there is more than one file libGL.so present on your system, make sure you use the best one;  i.e. the one that corresponds to your accelerated graphics.




-------------------------------------------------------

## what is special about this project?
Uses the C++ programming language and fully modern OpenGL methods, with textures, shaders and uniforms.  Achieves [at least] version 3.3 core profile contexts.  Compiles and runs on Windows, GNU/Linux and Mac OSX systems.

Focusing on portability and open source freedom, this project relies on SDL2, a PNG-loader by Lode Vandevenne, and OpenAL-Audio.

------------------------------------------------------------
Open source developers are welcome to help improve or extend this app.
Developer or not, send comments, suggestions or questions to:
fastrgv@gmail.com




## Legal Mumbo Jumbo:

This app is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2022  <fastrgv@gmail.com>

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

It is my intention to use media with copyrights or licenses that are compatible with GPLv3. Please notify me if you believe there is an incompatibility, and it will be removed ASAP, eg a CC-by-NC license is NOT GPL compatible.



### SoundFiles
...are either public domain or are from freesound.org and covered by the Creative Commons CC0 license documented in the accompanying file ./docs/creativeCommonsCC0.txt.   See "small-applause.txt" for details and URL.


### ImageFiles (x.png)
...for text-textures were created using gimp and are also covered by the GNU GPL v3 license.  Thanks to unluckystudio.com [Sujit Kumar Yadav] for car sprites, whose colors I modified slightly with GIMP, and to OpenGameArt.org for the playing card symbols under a cc-by-3.0 license (see http://creativecommons.org/) uploaded there by IronStarMedia.co.uk


### LodePNG (png loader module: lodepng.cpp lodepng.h)
are files copyrighted by Lode Vandevenne and so marked with all the details of their permitted uses near the tops of those two files.

### Other Credits and Thanks:
Serhiy Grabarchuk and Peter Grabarchuk for their "Hole in One", "Hole in One plus 4", "Nine", and "Four Suits" puzzles.

Nick Baxter, J.H.Conway, Jim Lewis, Bob Henderson, Gil Dogon, Ed Pegg Jr., J.I. Wiley, J.H. Fleming, C. L. Diamond, Sam Loyd, H. E. Dudeney, E. B. Escott, Nob Yoshigahara, James W. Stephens for the classic sliders.

----------------------------------------------------------
tags:  kids, puzzle, rush-hour, klotski, slider

----------------------------------------------------------

## Download Site for all my games:
https://github.com/fastrgv?tab=repositories
https://www.indiedb.com/members/fastrgv/games
https://fastrgv.itch.io
https://sourceforge.net/u/fastrgv/profile/
https://gamejolt.com/@fastrgv/games

====================================================

## Older Revision History

**ver 3.2.3 -- 27apr22**
* Repaired errors in "gmg" and "linkRings".
* Improved sound code.


**ver 3.2.2 -- 25apr22**
* Refined libs, scripts.
* Removed unused SFML libs.
* Updated lodepng.
* Added a 64-bit Windows build.

**ver 3.2.1 -- 22nov20**
* Improved sound code for robustness;
* Threads now created as "joinable".

**ver 3.2.0 -- 19nov20**
* All new sound system using Pthreads and OpenAL.
* Completely elliminated SFML-audio.
* Updated SDL2 to v2.0.12


**ver 3.1.1 -- 16oct20**
* Made further improvements in linux sound coding.
* Improved sound effects; now all stereo, and not too loud.
* Improved texture handling.

**ver 3.1.0 -- 23jan20**
* Fixed linux failure on RedHat using new sound system. Now runs on RedHat-S.L.7.8, Debian-Mint, & OpenSuse.
* OSX & Windows still using SFML libs.

**ver 3.0.0 -- 22jan20**
* Put codes into ./src/.
* Quantum improvement in Linux portability by removing sfml (linux only).


**ver 2.9.3 -- 27nov19**
* Removed bad library files from GNU/Linux build that prevented execution.

**ver 2.9.2 -- 25aug19**
* Updated to SDL2 v209;
* Solvers now ignore "="-key AFTER win (as they should);
* Added debug output of object selection to terminal window;
* Object selections can, in most cases, now be made using either left or right mouse button;
* Fixed error in using p-key/n-key (Previous/Next) in dirty12;

**ver 2.9.1 -- 7mar19**
* Generalized EXEs to allow calling from "home" directory, as well as the directory that contains them.

**ver 2.9.0 -- 7jan19**
* Repaired block selection errors;
* Added mouse drag as initiator of block moves;
* Improved "rush" exit animation;




