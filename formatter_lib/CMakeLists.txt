cmake_minimum_required(VERSION 3.16)
set(CMAKE_CXX_STANDARD 17)
project(formatter_lib)
add_library(${PROJECT_NAME} STATIC
${CMAKE_CURRENT_SOURCE_DIR}/formatter.h
${CMAKE_CURRENT_SOURCE_DIR}/formatter.cpp
)
