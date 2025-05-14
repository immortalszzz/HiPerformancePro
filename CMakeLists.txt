cmake_minimum_required (VERSION 3.2)
project (leptjson_test CXX)

include_directories(src)

if (CMAKE_C_COMPILER_ID MATCHES "GNU|Clang")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -ansi -pedantic -Wall")
endif()

add_library(leptjson src/leptjson.cpp)
add_executable(leptjson_test tests/test.cpp)
target_link_libraries(leptjson_test leptjson)
