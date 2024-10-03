cmake_minimum_required(VERSION 3.20)
set(PROJECT_URL "https://github.com/LudovicDeMatteis/crocoddyl-cmake-example-project.git")
set(PROJECT_NAME crocoddyl-cmake-example-project)
set(PROJECT_DESCRIPTION "Example of CMake project using crocoddyl")

set(CMAKE_DISABLE_WERROR True)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include(cmake/base.cmake)
compute_project_args(PROJECT_ARGS LANGUAGES CXX)
project(${PROJECT_NAME} ${PROJECT_ARGS})
set(CMAKE_VERBOSE_MAKEFILE False)

find_package(crocoddyl REQUIRED)

add_executable(main main.cpp)
target_link_libraries(main PRIVATE crocoddyl::crocoddyl)

