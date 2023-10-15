cmake_minimum_required(VERSION 3.23)
set(CMAKE_CXX_STANDARD 20)

# Set the project name
project(cs2pp)

# Nanobind
set(NB_SHARED OFF CACHE INTERNAL "")
add_subdirectory(vendor/nanobind)

# Main subdirectories
add_subdirectory(cs2proto)  # Protos
add_subdirectory(cs2pp)  # Library
add_subdirectory(cs2d)  # CLI
