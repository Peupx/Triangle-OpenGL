cmake_minimum_required(VERSION 4.1.2)
project(OpenGLTest VERSION 1.0.0)
cmake_policy(SET CMP0072 NEW)

find_library(GLFW_LIB 
    NAMES glfw3 glfw 
    PATHS "dependencies/lib"
)
find_package(OpenGL REQUIRED)

add_executable(OpenGLTest
    src/config.h
    src/main.cpp
    src/glad.c
    src/triangle_mesh.h
    src/triangle_mesh.cpp
)

target_include_directories(OpenGLTest PRIVATE dependencies)
target_link_libraries(OpenGLTest PRIVATE ${GLFW_LIB} OpenGL::GL)
