cmake_minimum_required(VERSION 3.10)
project(esepp)

# DEFAULTS
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmakeModules")

# ROOT
message(STATUS "")
message(STATUS ">>> Setting up ROOT.")
find_package(ROOT 5.34.04 REQUIRED "MathMore" "Foam")
include_directories(${ROOT_INCLUDE_DIR})

# Executable
add_executable(esepp esepp.cxx)

# LINKING
TARGET_LINK_LIBRARIES(esepp ${ROOT_LIBS} ${CLHEP_LIBRARIES} )
