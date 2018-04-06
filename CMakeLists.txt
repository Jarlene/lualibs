cmake_minimum_required(VERSION 3.10)
project(Lualibs)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")
find_package(Lua REQUIRED)
add_subdirectory(zlib)
add_subdirectory(json)
