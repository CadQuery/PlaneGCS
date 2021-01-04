cmake_minimum_required(VERSION 3.10)
project(GCS CXX)
set(CMAKE_CXX_STANDARD 17)

find_package(Eigen3 3.3 REQUIRED NO_MODULE)
find_package(Boost COMPONENTS graph)

SET(PlaneGCS_SRCS
    src/GCS.cpp
    src/GCS.h
    src/Util.h
    src/Geo.cpp
    src/Geo.h
    src/Constraints.cpp
    src/Constraints.h
    src/SubSystem.cpp
    src/SubSystem.h
    src/qp_eq.cpp
    src/qp_eq.h
)
#SOURCE_GROUP("PlaneGCS" FILES ${PlaneGCS_SRCS})

add_library(PlaneGCS SHARED ${PlaneGCS_SRCS})
target_link_libraries (PlaneGCS Eigen3::Eigen Boost::graph)
