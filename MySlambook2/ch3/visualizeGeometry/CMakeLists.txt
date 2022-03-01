cmake_minimum_required(VERSION 3.21)
project(visualizeGeometry)

set(CMAKE_CXX_STANDARD 14)

include_directories("/usr/include/eigen3")

find_package(Pangolin)
include_directories(${Pangolin_INCLUDE_DIRS})

add_executable(visualizeGeometry main.cpp)
target_link_libraries( visualizeGeometry ${Pangolin_LIBRARIES})

