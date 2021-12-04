cmake_minimum_required(VERSION 3.14)

set(CMAKE_CXX_STANDARD 11)

find_package(glfw3 REQUIRED)

add_library(glad src/vendor/glad/glad.c)
target_link_libraries(glad dl)
target_include_directories(glad PUBLIC src/vendor/glad/include)

add_executable(grphx src/main.cpp)
target_link_libraries(grphx PUBLIC glfw)
target_link_libraries(grphx PUBLIC glad)
