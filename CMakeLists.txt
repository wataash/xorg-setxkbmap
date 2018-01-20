cmake_minimum_required(VERSION 3.8)
project(xorg-setxkbmap)

set(CMAKE_VERBOSE_MAKEFILE on)

file(GLOB_RECURSE SRCS "*.c" "*.h")

add_executable(zdummy ${SRCS})

add_custom_target(setxkbmap COMMAND cd ${PROJECT_SOURCE_DIR}/build && make)

include_directories(
    build/
)

add_definitions(-DHAVE_CONFIG_H)
