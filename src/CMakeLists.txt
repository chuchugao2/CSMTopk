cmake_minimum_required(VERSION 3.6.3)
set(CMAKE_CXX_STANDARD 17)
set(SRCS main.cpp)
FIND_PACKAGE( OpenMP REQUIRED)
set(CMAKE_BUILD_WITH_INSTALL_RPATH TRUE)
add_subdirectory(graph)
add_subdirectory(utils)
add_subdirectory(matching)

add_executable(csm ${SRCS})
target_link_libraries(csm graph util match)
set_target_properties(csm PROPERTIES INSTALL_RPATH "$ORIGIN/lib")
SET(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -Wall -g -ggdb")
#PRINT_DEBUG COMPUTE_TRACK
add_compile_definitions()
