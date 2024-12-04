cmake_minimum_required(VERSION 3.22)

project(MyFirstJuceProject VERSION 0.0.1)

find_package(juce CONFIG REQUIRED)

add_subdirectory(AudioPlugin)