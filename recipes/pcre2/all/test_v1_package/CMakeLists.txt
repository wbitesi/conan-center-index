cmake_minimum_required(VERSION 3.1)
project(test_package LANGUAGES C)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(PCRE2 REQUIRED 8BIT CONFIG)

add_executable(${PROJECT_NAME} ../test_package/test_package.c)
target_link_libraries(${PROJECT_NAME} PRIVATE PCRE2::8BIT)
