cmake_minimum_required(VERSION 3.21)
project(plotTrajectory)

set(CMAKE_CXX_STANDARD 14)

include_directories("/usr/include/eigen3")
add_executable(coordinateTransform main.cpp)

find_package(Pangolin REQUIRED)
include_directories(${Pangolin_INCLUDE_DIRS})

add_executable(plotTrajectory plotTrajectory.cpp)
target_link_libraries(plotTrajectory ${Pangolin_LIBRARIES})
