cmake_minimum_required(VERSION 3.5)

project(using-submodule-test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(extern/submodule-test)

add_executable(using-submodule-test
    main.cpp
)

target_include_directories(${PROJECT_NAME} PRIVATE extern/submodule-test/include)
target_link_libraries(${PROJECT_NAME} sub::module1)
