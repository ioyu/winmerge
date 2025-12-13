cmake_minimum_required(VERSION 3.10)
project(WinMergeCore)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Define the library
add_library(WinMergeCore STATIC)

# Add source files
file(GLOB_RECURSE SOURCES "src/*.cpp" "src/*.c")
target_sources(WinMergeCore PRIVATE ${SOURCES})

# Add include directories
target_include_directories(WinMergeCore
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src
        Externals/boost
        Externals/poco/Foundation/include
        Externals/crystaledit/editlib
)
