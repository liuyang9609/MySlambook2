cmake_minimum_required(VERSION 3.21)
project(useSophus)

set(CMAKE_CXX_STANDARD 14)

find_package(Sophus REQUIRED)

include_directories("/usr/include/eigen3")
add_executable(useSophus main.cpp)
target_link_libraries(useSophus Sophus::Sophus)


