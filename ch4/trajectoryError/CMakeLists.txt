cmake_minimum_required(VERSION 3.21)
project(trajectoryError)

set(CMAKE_CXX_STANDARD 14)

option(USE_UBUNTU_20 "Set to ON if you are using Ubuntu 20.04" OFF)
find_package(Pangolin REQUIRED)

if (USE_UBUNTU_20)
    message("You are using Ubuntu 20.04, fmt::fmt will be linked")
    find_package(fmt REQUIRED)
    set(FMT_LIBRARIES fmt::fmt)
endif ()

include_directories(${Pangolin_INCLUDE_DIRS})

add_executable(trajectoryError main.cpp)
target_link_libraries(trajectoryError ${Pangolin_LIBRARIES} ${FMT_LIBRARIES})
