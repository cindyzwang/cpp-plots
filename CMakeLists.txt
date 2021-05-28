cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# set the project name
project(Plots VERSION 1.0)

configure_file(Plots.h.in Plots.h)

add_executable(plots main.cpp)

# Link matplotplusplus
find_package(Matplot++ REQUIRED)
target_link_libraries(plots PUBLIC Matplot++::matplot)

# add the binary tree to the search path for include files so that we will find TutorialConfig.h
target_include_directories(plots PUBLIC
                           "${PROJECT_BINARY_DIR}"
                          )
