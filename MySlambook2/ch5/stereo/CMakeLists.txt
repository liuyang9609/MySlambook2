cmake_minimum_required(VERSION 3.21)
project(stereo)

set(CMAKE_CXX_STANDARD 14)

find_package(Pangolin REQUIRED)

add_executable(stereo main.cpp)
find_package(OpenCV REQUIRED)
target_link_libraries(stereo ${OpenCV_LIBS} ${Pangolin_LIBRARIES})
