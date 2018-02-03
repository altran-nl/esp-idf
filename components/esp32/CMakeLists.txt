cmake_minimum_required(VERSION 3.5)
include(CTest)

set(ABCD_MODEL_SOURCE
        abcd_model.c
        abcd_model.h
        )

add_library(abcd_model STATIC ${ABCD_MODEL_SOURCE})

target_include_directories(abcd_model
        PUBLIC include
        PRIVATE src
        )
#
add_executable (abcd_model_test abcd_model.test.c)
target_link_libraries(abcd_model_test abcd_model)
#
add_test (Context     abcd_model_test context           )
add_test (Domains     abcd_model_test domains           )
add_test (Subjects    abcd_model_test subjects          )
add_test (Devices     abcd_model_test devices           )
add_test (Properties  abcd_model_test properties        )
add_test (ValueUpdate abcd_model_test update_value      )
