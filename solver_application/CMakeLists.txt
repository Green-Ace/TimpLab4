cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)

project(solver_app)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

add_executable(solver
    equation.cpp
)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib
    {CMAKE_CURRENT_SOURCE_DIR}/lib_solver_build)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
    {CMAKE_CURRENT_SOURCE_DIR}/lib_formatter_build)

target_link_libraries(solver PUBLIC formatter_ex_lib formatter_lib solver_lib)
