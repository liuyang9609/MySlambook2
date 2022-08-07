cmake_minimum_required(VERSION 3.21)
project(g2o_BA)

set(CMAKE_CXX_STANDARD 14)

LIST(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
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

add_executable(g2o_BA main.cpp)
add_library(bal_common common.cpp)
target_link_libraries(g2o_BA ${G2O_LIBS} bal_common)
