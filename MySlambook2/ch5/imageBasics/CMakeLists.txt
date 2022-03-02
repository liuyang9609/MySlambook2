cmake_minimum_required(VERSION 3.21)
project(imageBasics)

set(CMAKE_CXX_STANDARD 14)

add_executable(imageBasics main.cpp)
find_package(OpenCV REQUIRED)
target_link_libraries(imageBasics ${OpenCV_LIBS})

add_executable(undistortImage undistortImage.cpp)
find_package(OpenCV REQUIRED)
target_link_libraries(undistortImage ${OpenCV_LIBS})
