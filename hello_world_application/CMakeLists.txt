cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)

project(hello_world)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

add_executable(hw
    hello_world.cpp
)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
    {CMAKE_CURRENT_SOURCE_DIR}/lib_build)

target_link_libraries(hw PUBLIC formatter_ex_lib formatter_lib)
