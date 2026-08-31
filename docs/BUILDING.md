# Building from source

This document describes the build setup currently used for **These Aren't the Heads You're Looking For**.

## Requirements

- Windows 10 or Windows 11
- Visual Studio 2022 with C++ development tools
- CMake
- Git
- A recursive checkout of RE-UE4SS

The mod is currently built against this RE-UE4SS revision:

    a1e7f571c789f63f3de6773d056be6f778c14dc8

This corresponds to the UE4SS build used during development:

    UE4SS v3.0.1 Beta #0

Using another revision may work, but has not been tested.

## 1. Clone RE-UE4SS

Clone RE-UE4SS recursively so that its required submodules are available.

Example:

    git clone --recursive https://github.com/UE4SS-RE/RE-UE4SS.git C:\src\RE-UE4SS

Then switch to the revision used by this project:

    cd C:\src\RE-UE4SS
    git checkout a1e7f571c789f63f3de6773d056be6f778c14dc8
    git submodule update --init --recursive

## 2. Configure the project

From the root of this repository:

    cmake -S . -B build -G "Visual Studio 17 2022" -A x64 -DRE_UE4SS_SOURCE_DIR="C:\src\RE-UE4SS"

If CMake is installed through Visual Studio and is not available in PATH, its executable may be located somewhere similar to:

    C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe

## 3. Build

Build the shipping configuration:

    cmake --build build --config Game__Shipping__Win64 --target TheseArentTheHeadsYoureLookingFor

The resulting mod DLL should be created at:

    build\Game__Shipping__Win64\main.dll

## 4. Test in game

Create the following UE4SS mod structure:

    ue4ss
    └─ Mods
       └─ TheseArentTheHeadsYoureLookingFor
          ├─ enabled.txt
          └─ dlls
             └─ main.dll

`enabled.txt` can be an empty file. Its presence enables the mod through UE4SS without requiring an entry in `mods.txt`.

Launch Star Wars Zero Company normally.

A successful load should produce a UE4SS log entry similar to:

    Starting C++ mod 'TheseArentTheHeadsYoureLookingFor'
## Notes

The first build can take significantly longer because RE-UE4SS and its dependencies are compiled as part of the build tree.

Subsequent builds are much faster as long as the `build` directory is kept.

The repository intentionally does not contain:

- RE-UE4SS source code
- game files
- extracted game assets
- `.usmap` files
- precompiled build intermediates
- local debugging logs

The release package only needs the compiled `main.dll` inside the correct UE4SS mod directory structure.
