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

## To Edit:  
If you wish to add another preset, 
Copy and paste an existing base preset.  
Pop it beneath the existing base presets and rename it accordingly. 

Then take a preset collection, whichever is the closest to the one you are wanting to implement, again, copy and paste the entire collection, to the bottom of the file.
Rename to reflect tothe new base you have just created, and make sure the inherit tag reflects your new base preset.

### Eg:
The followng code is example only.  Not really a good idea to copy and paste it.  
Use the code within the file.   

copy a base preset:  

        ...  other base presets...  
        {
            "name": "ms-clang-base",
            "inherits": "base",
            "hidden": true,
            "cacheVariables": {
                "CMAKE_C_COMPILER": "clang.exe",
                "CMAKE_CXX_COMPILER": "clang++.exe"
            }
        },
        ...  

paste and change:  

        ... other base presets...   
        {
            "name": "intel-linux-base",
            "inherits": "base",
            "hidden": true,
            "cacheVariables": {
                "CMAKE_C_COMPILER": "icx.exe",
                "CMAKE_CXX_COMPILER": "icpx.exe"
            }
        },
        ...  
        
copy a compiler preset...  

      ...  other compiler presets...  
        {
            "name": "clang-cl-debug",
            "displayName": "Clang Cl Debug",
            "inherits": "clang-cl-base",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "Debug"
            }
        },
        {
            "name": "clang-cl-release",
            "displayName": "Clang Cl Release",
            "inherits": "clang-cl-debug",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "Release"
            }
        },
        {
            "name": "clang-cl-relwithdebinfo",
            "displayName": "Clang Cl Release With Debug Info",
            "inherits": "clang-cl-debug",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "RelWithDebInfo"
            }
        },
        ...  
        
paste and change:  

        ... other compiler presets...  
        {
            "name": "intel-linux--debug",
            "displayName": "Intel Linux Debug",
            "inherits": "intel-linux-base",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "Debug"
            }
        },
        {
            "name": "intel-linux-release",
            "displayName": "Intel Linux Release",
            "inherits": "intel-linux-debug",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "Release"
            }
        },
        {
            "name": "intel-linux-relwithdebinfo",
            "displayName": "Intel Linux Release With Debug Info",
            "inherits": "intel-linux-debug",
            "cacheVariables": {
                "CMAKE_BUILD_TYPE": "RelWithDebInfo"
            }
        },
        ...  
        
### Note:
I'm not intending to do much, if any, maintenance on this file, it's the sort of file which shouldn't need much work on it. 
If you experience any problems with it, I would, personally, head over to the cmake forums:  
CMake Discourse (https://discourse.cmake.org/)  
I'm not, in any shape or form, an expert on CMake; not at all (truly, not a fan either), so I don't spend a lot of time on cmake, preferring the auto tools of Qt Creator and such like. 
I use this file for my work, simply to save time and effort trying to work out what on earth CMake is trying to do this time... 
