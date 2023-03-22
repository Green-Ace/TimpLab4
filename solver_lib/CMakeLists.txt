cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)

project(solver_lib)

add_library(${PROJECT_NAME} STATIC
    ${CMAKE_CURRENT_SOURCE_DIR}/solver.h
    ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp
)
