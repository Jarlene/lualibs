
cmake_minimum_required(VERSION 3.10)
project(zlib)

include_directories(${LUA_INCLUDE_DIR})
FIND_PACKAGE(ZLIB REQUIRED)

INCLUDE_DIRECTORIES(${ZLIB_INCLUDE_DIRS} ${LUA_INCLUDE_DIR})
ADD_LIBRARY(zlib MODULE lua_zlib.c zlib.def)
SET_TARGET_PROPERTIES(zlib PROPERTIES PREFIX "")
SET_TARGET_PROPERTIES(zlib PROPERTIES OUTPUT_NAME zlib)
TARGET_LINK_LIBRARIES(zlib ${ZLIB_LIBRARIES} ${LUA_LIBRARIES})