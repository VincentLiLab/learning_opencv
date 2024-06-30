cmake_minimum_required(VERSION 3.26)

project(learning_opencv VERSION 1.0.0 LANGUAGES C CXX)

find_package( OpenCV REQUIRED )

include_directories( ${OpenCV_INCLUDE_DIRS} )

message(${OpenCV_INCLUDE_DIRS})

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")

add_executable(learning_opencv main.cpp)

target_include_directories(learning_opencv PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )

target_link_libraries( learning_opencv ${OpenCV_LIBS} )

include("${CMAKE_SOURCE_DIR}/cmake/Helper.cmake")

internal_add_subdirectorys(modules)