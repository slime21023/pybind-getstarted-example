cmake_minimum_required(VERSION 3.4...3.18)
project(example LANGUAGES CXX)
set(CMAKE_CXX_COMPILER "/usr/bin/clang++")

add_subdirectory(pybind11)
pybind11_add_module(example src/main.cpp)
set(CMAKE_CXX_STANDARD_REQUIRED ON)  
set(CMAKE_CXX_EXTENSIONS OFF) 
find_package (Python3 COMPONENTS Interpreter Development)

set(CMAKE_CXX_STANDARD 11)  # or 11, 14, 17, 20
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -v -stdlib=libc++")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -stdlib=libc++ -lc++abi")