# JUCE Project Setup Guide with vcpkg
This guide walks through setting up a JUCE project using vcpkg as the package manager.

## Prerequisites
- VSCode with C++ extensions
- CMake
- Git
- Xcode (for compiler)

## Initial Setup
1. Create and initialize your project:
```zsh
mkdir my-audio-plugin
cd my-audio-plugin
git init
```

2. Add vcpkg as a git submodule:
```zsh
git submodule add https://github.com/microsoft/vcpkg
```

3. Bootstrap vcpkg (with metrics disabled):
```zsh
./vcpkg/bootstrap-vcpkg.sh -disableMetrics
```

4. Create a new application manifest:
```zsh
./vcpkg/vcpkg new --application
```

5. Add JUCE as a dependency:
```zsh
./vcpkg/vcpkg add port juce
```

## Project Configuration
1. Create the basic CMakeLists.txt:
```cmake
cmake_minimum_required(VERSION 3.22)
project(enterprojectname)
find_package(juce CONFIG REQUIRED)
```

2. Create CMakePresets.json:
See CMakePresets.json in this repo for the content - it sets up the build configuration for Xcode.

3. Configure and build using the preset:
```zsh
cmake --preset buildx2
cmake --build build
```

## Next Steps
After this setup, you can:
1. Add your source files
2. Expand the CMakeLists.txt for your specific plugin needs
3. Build and test your project