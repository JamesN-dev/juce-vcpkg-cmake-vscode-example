# JUCE CMake vcpkg VSCode Setup
How I set up my VSCode development environment for JUCE audio plugins using CMake and vcpkg on Mac. Includes a working "Hello World" plugin to verify everything's configured correctly.

## What This Is
- My working VSCode dev setup for JUCE
- Basic "Hello World" plugin example
- Uses CMake + vcpkg instead of Projucer
- Happens to use Xcode's compiler (we're on Mac after all)
- Builds AU, VST3, and Standalone formats

## Requirements
- VSCode with C++ extensions
- CMake 3.22+
- Git
- Xcode (just for the compiler)

## Getting Started
1. Clone it:
```bash
git clone github.com:JamesN-dev/juce-vcpkg-cmake-vscode-example.git
cd cpp_test
```

2. Set up vcpkg:
```bash
git submodule add https://github.com/microsoft/vcpkg
./vcpkg/bootstrap-vcpkg.sh -disableMetrics
```

3. Configure & Build:
```bash
cmake --preset buildx2
cmake --build build
```

Plugins end up in:
- `build/AudioPlugin/AudioPluginExample_artefacts/VST3/`
- `build/AudioPlugin/AudioPluginExample_artefacts/AU/`
- `build/AudioPlugin/AudioPluginExample_artefacts/Standalone/`

Once built, you can run the standalone version to see "Hello World!" - if you see it, everything's working!

## VSCode Setup
See SETUP.md for the detailed guide on getting VSCode configured from scratch.

## Project Structure
```
cpp_test/
├── CMakeLists.txt     # Build setup
├── CMakePresets.json  # Build presets
├── AudioPlugin/       # Plugin code (Hello World example)
└── vcpkg/            # Package manager
```
