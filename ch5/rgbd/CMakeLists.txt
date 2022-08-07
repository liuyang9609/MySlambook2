cmake_minimum_required(VERSION 3.21)
project(rgbd)

set(CMAKE_CXX_STANDARD 14)

find_package(Sophus REQUIRED)
include_directories(${Sophus_INCLUDE_DIRS})

find_package(Pangolin REQUIRED)

add_executable(rgbd main.cpp)
find_package(OpenCV REQUIRED)
target_link_libraries(rgbd ${OpenCV_LIBS} ${Pangolin_LIBRARIES})
