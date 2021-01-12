cmake_minimum_required(VERSION 3.10)

project(TestDemo)

# 编译参数
add_compile_options(-std=c++11)
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g -ggdb")
set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")

# 项目版本
set(VERSION_MAJOR 1)
set(VERSION_MINOR 2)

# 文件替换
configure_file(
    "${PROJECT_SOURCE_DIR}/buildConfig.h.in"
    "${PROJECT_BINERY_DIR}/src/buildConfig.h"
)

# 替换后的目录包含
include_directories(${PROJECT_BINERY_DIR}/src)

# 添加源文件目录
add_subdirectory(${PROJECT_SOURCE_DIR}/src)
