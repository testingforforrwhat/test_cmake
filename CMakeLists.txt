cmake_minimum_required(VERSION 3.0)
project(test_cmake)

add_executable(test_cmake test_alsa.c)

target_link_libraries(${PROJECT_NAME} asound)

