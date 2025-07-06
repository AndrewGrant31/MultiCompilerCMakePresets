# Multi-Compiler CMake Presets JSON file
a cmake presets file for multi-compiler setups  
This cmake-presets file is for use with multi-compiler setups.

# Note:  
## Some of the compiler directives may need changing, depending on your sepcific needs and use cases

## Tested on:
- MS Windows 11:
  - Visual Studio 2022 (MSVC)
  - Visual Studio 2022 (Cl-Clang)
  - Visual Studio 2022 (WSL2)
    - gcc/g++
    - clang/clang++  
  - Visual Studio Code
      - gcc/g++
      - clang/clang++
      - 
- Ubuntu 24.04
  - gcc/g++
  - clang/clang++
- OpenSuse Tumbleweed (July 2025)
  - gcc/g++
  - clang/clang++ 

## Install:
Pop it in the projects' root folder, next to projects' main CMakeLists.txt file. That should be enough to ensure it's use.

### Note:
I'm not intending to do much, if any, maintenance on this file, it's the sort of file which shouldn't need much work on it. 
If you experience any problems with it, I would, personally, head over to the cmake forums:  
CMake Discourse (https://discourse.cmake.org/)  
I'm not, in any shape or form, an expert on CMake; not at all (truly, not a fan either), so I don't spend a lot of time on cmake, preferring the auto tools of Qt Creator and such like. 
I use this file for my work, simply to save time and effort trying to work out what on earth CMake is trying to do this time... 
