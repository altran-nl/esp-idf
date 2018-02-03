cmake_minimum_required(VERSION 3.5)
file(GLOB DRIVER_SRC
        "include/*.h"
        "*.c"
        )

add_library(driver ${DRIVER_SRC})