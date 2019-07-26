cmake_minimum_required(VERSION 3.1)
project(rnnoise)

# Get source files
file(GLOB SOURCES "src/*.c" "src/*.h" "include/*.h")

# Compile the library
add_library(rnnoise STATIC ${SOURCES})

# Include dirs
target_include_directories(rnnoise PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:include>
        PRIVATE src)