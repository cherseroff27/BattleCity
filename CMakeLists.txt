cmake_minimum_required(VERSION 4.0.3 FATAL_ERROR)

set(PROJECT_NAME BattleCity)
project(${PROJECT_NAME})

add_executable(${PROJECT_NAME} src/main.cpp)

include_directories(external/glfw/include)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

add_subdirectory(external/glfw)
target_link_libraries(${PROJECT_NAME} glfw)

add_subdirectory(external/glad)
target_link_libraries(${PROJECT_NAME} glad)