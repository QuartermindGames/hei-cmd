cmake_minimum_required(VERSION 3.16)
project(hei-cmd)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY $<1:${CMAKE_SOURCE_DIR}/bin/>)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY $<1:${CMAKE_SOURCE_DIR}/lib/>)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY $<1:${CMAKE_SOURCE_DIR}/bin/>)

if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unused-function")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wno-unused-function")
elseif ("${CMAKE_C_COMPILER_ID}" STREQUAL "MSVC")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -W3")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -W3")
endif ()

add_subdirectory(src/hei/plcore)
add_subdirectory(src/hei/plgraphics)
add_subdirectory(src/hei/plmodel)

add_subdirectory(src/plugins/blitz)
add_subdirectory(src/plugins/core)
add_subdirectory(src/plugins/valve)

set(CMAKE_C_STANDARD 11)
add_subdirectory(src/cmd)
