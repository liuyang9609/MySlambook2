cmake_minimum_required(VERSION 3.21)
project(cere_BA)

set(CMAKE_CXX_STANDARD 14)

list( APPEND CMAKE_MODULE_PATH /home/liuyang/MySLAM/SLAMProgramming/MySlambook2/ch9/cere_BA/cmake)
SET(G2O_LIBS g2o_csparse_extension g2o_stuff g2o_core cxsparse)

# OpenCV
#find_package(OpenCV REQUIRED)
#include_directories(${OpenCV_INCLUDE_DIRS})

# Ceres
find_package(Ceres REQUIRED)
include_directories(${CERES_INCLUDE_DIRS})

# g2o
set(G2O_ROOT /usr/local/include/g2o)
find_package(G2O REQUIRED)
include_directories(${G2O_INCLUDE_DIRS})

# Eigen
find_package(Eigen3 REQUIRED)
include_directories("/usr/include/eigen3")

#Sophus
find_package(Sophus REQUIRED)

#CSparse
find_package(CSparse REQUIRED)
include_directories(${CSPARSE_INCLUDE_DIR})

add_library(bal_common common.cpp)
add_executable(cere_BA main.cpp)
target_link_libraries(cere_BA ${CERES_LIBRARIES} bal_common)
