cmake_minimum_required(VERSION 3.10)

project(TestDemo)

add_definitions(-std=c++11)
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g -ggdb")
set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")

set(VERSION_MAJOR 1)
set(VERSION_MINOR 0)

configure_file(
    "${PROJECT_SOURCE_DIR}/buildConfig.h.in"
    "${PROJECT_BINERY_DIR}/src/buildConfig.h"
)

include_directories(${PROJECT_BINERY_DIR}/src)

add_subdirectory(${PROJECT_SOURCE_DIR}/src)
