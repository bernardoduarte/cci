cmake_minimum_required(VERSION 3.5.1 FATAL_ERROR)

project(CCI VERSION 0.1.0 LANGUAGES C)

add_compile_options(-Wall -Wextra -Wpedantic)

add_executable(helloworld main.c)