cmake_minimum_required(VERSION 3.22)
project(func_graph_drawer LANGUAGES CXX)

# vcpkg path
set(CMAKE_TOOLCHAIN_FILE "vcpkg/scripts/buildsystems/vcpkg.cmake" CACHE STRING "Vcpkg toolchain file")

# SDL2 path
list(APPEND CMAKE_PREFIX_PATH "vcpkg/installed/x64-windows-static/share/sdl2")

find_package(SDL2 CONFIG REQUIRED)

add_executable(func_graph_drawer src/main.cpp)

target_compile_features(func_graph_drawer PRIVATE cxx_std_20)

target_link_libraries(func_graph_drawer PRIVATE SDL2::SDL2)
target_link_libraries(func_graph_drawer PRIVATE SDL2::SDL2main)
