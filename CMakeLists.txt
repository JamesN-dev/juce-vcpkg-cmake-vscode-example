cmake_minimum_required(VERSION 3.22)

# Name the project something descriptive and generic
project(JUCEAudioPlugins)

# Find JUCE package
find_package(juce CONFIG REQUIRED)

# Add the AudioPlugin directory
add_subdirectory(AudioPlugin)