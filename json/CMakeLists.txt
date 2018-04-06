
cmake_minimum_required(VERSION 3.10)
project(cjson)

include_directories(${LUA_INCLUDE_DIR})

if(NOT USE_INTERNAL_FPCONV)
    # Use libc number conversion routines (strtod(), sprintf())
    set(FPCONV_SOURCES fpconv.c)
else()
    # Use internal number conversion routines
    set(FPCONV_SOURCES g_fmt.c dtoa.c)
endif()


add_library(cjson MODULE lua_cjson.c strbuf.c ${FPCONV_SOURCES})
set_target_properties(cjson PROPERTIES PREFIX "")
SET_TARGET_PROPERTIES(cjson PROPERTIES OUTPUT_NAME cjson)
target_link_libraries(cjson ${LUA_LIBRARIES})