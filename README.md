This is a simple modern OpenGL game for my project in  the alx course, It's a very simple 3D game where player starts in random position and needs to find exit in randomly generated (Depth-first search and recursive division algorithms) perfect maze. It's implemented using OpenGL, SDL2, mINI, GLM and GLAD libraries.
BUID GUIDE

1. Clone repository
2. Install SDL2, GLM and OpenGL development libraries
Linux

Install SDL2, GLM, OpenGL development libraries and cmake. For information about installing packages check manual of distribution you are using.
Windows

Download and install CMake. Also download SDL2 and GLM. Make sure to download development libraries for Visual C++. SDL2 and GLM are expected to be present in ext directory in source root. Create ext directory in source root and extract downloaded archives there. Change extracted directories names to SDL2 and glm respectively. If you wish to use different directories for dependencies modify CMakeLists.txt file to point SDL2_PATH and GLM_ROOT_DIR variables to selected directories. OpenGL should come with graphics drivers. Build was tested with Visual Studio 2022 Community Edition and also other previous versions(2017,2010) but due to the fact they do not support c++17 it didnt build well.
macOS

Build was tested with framework installation. Download and install CMake. Also download SDL2 and GLM. Install SDL2 framework into /Library/Frameworks directory. Create ext directory, extract GLM and put glm directory there. OpenGL framework is part of operating system. Command line developers tools are also needed.
3. Build

CMake is used to generate build configuration for each platform. On Windows use CMake to generate Visual Studio solution and use Visual Studio for building. On Linux and macOS use CMake to generate Makefile configuration and use make command to build.
4. Running

On Windows and Linux glmaze expects "assets" and "shaders" directory to be present in the same directory as executable. On macOS build generates App Bundle and these directories are automatically copied into generated bundle.
Manual
Configuration options

Configurations is specified by command line arguments or by ini configuration file. Command line options can be specified in any order and count. Command line arguments have higher priority and will override config file values.

-width=value - Window width

-height=value - Window height
Note: These values are respected only if game works in windowed mode. In fullscreen mode game always set desktop resolution. With custom window size both values (width and height) needs to be specified and height can't be bigger than width. Default size is 800x600.

-size=value - Maze size (Min is 10, max is 100000, default 20).
Note: For big mazes (more than 1000) it's better to use RD generator because DFS is pretty slow and generating big mazes will last long time even on fast CPU. Big mazes will also consume more memory. For 100000 size (RD generator) application consumes over 9 GiB of RAM.

-disable-collisions - Disable collisions

-fullscreen - Run in fullscreen mode

-generator=value - Select maze generator: "RD" for recursive division and "DFS" for depth-first search. Default is "RD".

-seed=value - Generator seed

-portable - Don't try to load or create config file

-disable-mouse - Disable mouse control

Controls

By default camera is controlled by mouse and W/S keys are used for moving forward/backward. When mouse control is disabled then camera is rotated left and right by A and D keys.
