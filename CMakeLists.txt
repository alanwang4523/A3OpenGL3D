cmake_minimum_required(VERSION 3.6)
project(A3OpenGL3D)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/modules/")

find_package(GLM REQUIRED)
find_package(GLEW REQUIRED)
find_package(GLFW3 REQUIRED)

message("<=======>")
message("FOUND GLM in ${GLM_FOUND}")
message("FOUND GLEW in ${GLEW_FOUND}")
message("FOUND GLFW3 in ${GLFW3_FOUND}")

file(GLOB_RECURSE CPP_FILES_IN_SRC ./src/*.cpp)
set(SOURCE_FILES ${CPP_FILES_IN_SRC} main.cpp)
add_executable(A3OpenGL3D ${SOURCE_FILES})

target_link_libraries(A3OpenGL3D glm::glm GLEW::GLEW glfw)
target_link_libraries(A3OpenGL3D "-framework OpenGL")
target_link_libraries(A3OpenGL3D "-framework GLUT")