cmake_minimum_required(VERSION 3.22)
# CMAKE_VERSION <major>.<minor>.<date>(YYMMDD) or <patch>
project(
  SudokuSolver
  VERSION 0.0.220821
  LANGUAGES CXX)
message("-- PROJECT = ${CMAKE_PROJECT_NAME} v${CMAKE_PROJECT_VERSION}")
list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/scripts/cmake")

# Set the compiler options
set(CMAKE_CXX_STANDARD 20) # > Set cmake Cxx standard to 11/14/17/20
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(MSVC)
  # warning level 4 and all warnings as errors
  add_compile_options(/W4 /WX)
else()
  # lots of warnings and all warnings as errors
  add_compile_options(-Wall -Wextra -pedantic -Werror)
endif()

# create main executable file
add_executable(${PROJECT_NAME} main.cpp)
include(Doxygen)
#Doxygen({CMAKE_SOURCE_DIR}/docs/doxygen-html {CMAKE_SOURCE_DIR})

#include(Format)
#Format(.)

#include(AddCppCheck)
#AddCppCheck({CMAKE_SOURCE_DIR})

#include(EnableCoverage, AddCoverage)
#EnableCoverage({CMAKE_SOURCE_DIR})
#AddCoverage({CMAKE_SOURCE_DIR})
