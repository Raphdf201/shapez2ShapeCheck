cmake_minimum_required(VERSION 3.30)
project(shapez2ShapeCheck)

set(CMAKE_CXX_STANDARD 23)

add_executable(lookup4 lookup.cpp)
add_executable(search4 search.cpp)
add_executable(lookup5 lookup.cpp)
add_executable(search5 search.cpp)

target_compile_definitions(lookup5 PRIVATE CONFIG_LAYER=5)
target_compile_definitions(search5 PRIVATE CONFIG_LAYER=5)
