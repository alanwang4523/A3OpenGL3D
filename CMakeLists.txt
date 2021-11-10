cmake_minimum_required(VERSION 3.6)
project(A3OpenGL3D)

set(CMAKE_CXX_STANDARD 11)

set(GLM_H /usr/local/Cellar/glm/0.9.9.8/include)
set(GLEW_H /usr/local/Cellar/glew/2.2.0_1/include)
set(GLFW_H /usr/local/Cellar/glfw/3.3.4/include)
include_directories(${GLM_H} ${GLEW_H} ${GLFW_H})

include_directories("/usr/local/include")

set(GLEW_LINK /usr/local/Cellar/glew/2.2.0_1/lib/libGLEW.2.2.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.3.4/lib/libglfw.3.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})

file(GLOB_RECURSE CPP_FILES_IN_SRC           ./src/*.cpp)

set(SOURCE_FILES ${CPP_FILES_IN_SRC} main.cpp)
add_executable(A3OpenGL3D ${SOURCE_FILES})

target_link_libraries(A3OpenGL3D "-framework OpenGL")
target_link_libraries(A3OpenGL3D "-framework GLUT")