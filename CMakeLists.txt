
cmake_minimum_required(VERSION 3.0)
project(mylib)

add_library(mylib SHARED mylib.cpp)

install(TARGETS mylib
        EXPORT  mylib_targets
        RUNTIME DESTINATION bin)

