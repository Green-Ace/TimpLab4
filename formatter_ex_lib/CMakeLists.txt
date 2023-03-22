cmake_minimum_required(VERSION 3.16)
set(CMAKE_CXX_STANDARD 17)
project(formatter_ex_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib)
add_library(${PROJECT_NAME} STATIC
${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.h
${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.cpp
)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib {CMAKE_CURRENT_SOURCE_DIR}/lib_build)
