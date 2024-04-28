cmake_minimum_required(VERSION 3.10)

project(learn_opengl3)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)

include_directories(${OPENGL_INCLUDE_DIRS})

set(GLFW_BUILD_DOCS OFF CACHE BOOL "GLFW lib only")
set(GLFW_INSTALL OFF CACHE BOOL "GLFW lib only")

add_subdirectory(lib/glfw)

include_directories(lib/glfw/include)
include_directories(lib/glad/include)

add_executable(learn_opengl3 src/main.cpp lib/glad/src/glad.c)

target_link_libraries(learn_opengl3 glfw ${OPENGL_LIBRARIES})
