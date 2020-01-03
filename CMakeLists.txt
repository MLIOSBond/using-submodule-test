cmake_minimum_required(VERSION 3.5)

project(using-submodule-test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#set(SUBMODULE_PROJECT_NAME "submodule-test" CACHE STRING "Name of the test submodule")
include("extern/submodule-test/cmake/includeAll.cmake")

add_executable(using-submodule-test
    main.cpp
    )
