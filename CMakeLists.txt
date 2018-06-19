# Specify minimum version fro CMake
cmake_minimum_required(VERSION 3.0)

# ensure c++14
set(CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_BUILD_TYPE Debug)

# check if it worked, ofc they did but check
if(CXX_STANDARD_REQUIRED)
  message("A meme to be sure!")
endif(CXX_STANDARD_REQUIRED)

if(CMAKE_CXX_STANDARD)
  message("But a welcome one")
endif(CMAKE_CXX_STANDARD)

# compiler flags
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")

# check if LD_LIBRARY_PATH is set -- I fkup up prolly something therefore linking fails.. lamost obselote
#if(LD_LIBRARY_PATH)
#  message("LD_LIBRARY_PATH IS SET")
#else()
#  set(LD_LIBRARY_PATH "/usr/local/lib")
#  message("ld is set in else branch!!")
#endif(LD_LIBRARY_PATH)

# Project'name 
project(divinitus)


# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

# The following folder will be included
include_directories("${PROJECT_SOURCE_DIR}/src")

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules/")

# SFML
find_package(SFML COMPONENTS graphics window system)
include_directories(${SFML_INCLUDE_DIR})
# lehetne normalias is...... ya nem
add_executable(divinitus ${PROJECT_SOURCE_DIR}/src/main.cpp)
target_link_libraries(divinitus ${SFML_LIBRARY_PATH})

