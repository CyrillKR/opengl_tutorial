cmake_minimum_required(VERSION 3.15)
project(GLFWProject C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(glfw3 REQUIRED)

add_executable(GLFWProject src/main.cpp src/glad.c)

target_include_directories(GLFWProject PRIVATE include)

# Link GLFW and the macOS OpenGL framework
target_link_libraries(GLFWProject PRIVATE glfw "-framework OpenGL")
