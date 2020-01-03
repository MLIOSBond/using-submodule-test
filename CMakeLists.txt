cmake_minimum_required(VERSION 3.5)

project(using-submodule-test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#set(SUBMODULE_PROJECT_NAME "submodule-test" CACHE STRING "Name of the test submodule")
include("extern/submodule-test/cmake/includeAll.cmake")

message(STATUS "Include path: ${SUBMODULE_TEST_INCLUDE_PATH}")


add_executable(using-submodule-test
    main.cpp

    ${SUBMODULE_TEST_INCLUDE_FILES}
    ${SUBMODULE_TEST_SOURCE_FILES}
    )

target_include_directories(using-submodule-test PRIVATE ${SUBMODULE_TEST_INCLUDE_PATH})
