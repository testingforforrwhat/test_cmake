cmake_minimum_required(VERSION 3.0)
project(test_cmake)

add_executable(test_cmake test_alsa.c)

#undefined reference to `snd_pcm_open'
#/usr/bin/ld: test_alsa.c:(.text+0x8c): undefined reference to `snd_strerror'

# if gcc
#gcc -o test_alsa test_alsa.c -lasound

# if cmake
#target_link_libraries(your_executable_name asound)

find_package(ALSA REQUIRED)
target_link_libraries(${PROJECT_NAME} asound)  # 将 ${PROJECT_NAME} 目标链接到 asound库



#target_link_libraries 和 find_package 在 CMake 中有不同的作用，不能相互替代使用。
#在使用 CMake 进行项目构建时，通常需要先通过 find_package 找到外部依赖库，然后再通过 target_link_libraries 将目标文件与库文件进行链接。
#find_package(Qt5 COMPONENTS Core Widgets Charts Multimedia REQUIRED)
#find_package 用于查找并加载外部依赖库，并定义相关变量，如 include 目录、库目录、库文件名等等。通过这些定义，CMake 将能够在生成 Makefile 时使用这些依赖库

