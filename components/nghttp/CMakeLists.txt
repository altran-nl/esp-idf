cmake_minimum_required(VERSION 3.5)
SET(CMAKE_C_COMPILER gcc)
file(GLOB_RECURSE NGHTTP_SRC
#        "*.h"
        "*.c"
        )
include_directories(include port/include)
add_library(nghttp ${NGHTTP_SRC})
