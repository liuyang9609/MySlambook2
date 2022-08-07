cmake_minimum_required(VERSION 3.21)
project(pose_graph_g2o_SE3)

LIST(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

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
set(CMAKE_CXX_STANDARD 14)

add_executable(pose_graph_g2o_SE3 main.cpp)
target_link_libraries(pose_graph_g2o_SE3
        g2o_core g2o_stuff g2o_types_slam3d
        ${CHOLMOD_LIBRARIES}
        )
