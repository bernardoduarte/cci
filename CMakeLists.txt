cmake_minimum_required(VERSION 3.5.1 FATAL_ERROR)

project(CCI VERSION 0.1.0 LANGUAGES C)

set(CMAKE_VERBOSE_MAKEFILE on)

link_libraries(-v)

option(ENABLE_COVERAGE "Enable coverage reporting for gcc/clang" FALSE)

if(ENABLE_COVERAGE)
	add_compile_options(--coverage -O0 -g)
endif()

add_compile_options(-Wall -Wextra -Wpedantic)

add_executable(helloworld main.c)
target_link_libraries(helloworld --coverage)

enable_testing()

add_executable(tester tester.c)
target_link_libraries(tester --coverage)

add_test(Tester tester)