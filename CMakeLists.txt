cmake_minimum_required( VERSION 3.1 )

project( GLFW-CMake-starter )

find_package( OpenGL REQUIRED )

include_directories( ${OPENGL_INCLUDE_DIRS} )

set( GLFW_BUILD_DOCS OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_INSTALL OFF CACHE BOOL  "GLFW lib only" )

add_subdirectory( glfw )

set( GLFW-CMAKE-STARTER-SRC
     main.cpp
     )
     
add_executable( GLFW-CMake-starter ${GLFW-CMAKE-STARTER-SRC} )
target_link_libraries( GLFW-CMake-starter ${OPENGL_LIBRARIES} glfw )