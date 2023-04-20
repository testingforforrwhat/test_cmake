cmake_minimum_required(VERSION 3.0)
project(test_cmake)

add_executable(test_cmake test_alsa.c)

#undefined reference to `snd_pcm_open'
#/usr/bin/ld: test_alsa.c:(.text+0x8c): undefined reference to `snd_strerror'

# if gcc
#gcc -o test_alsa test_alsa.c -lasound

# if cmake
#target_link_libraries(your_executable_name asound)

#target_link_libraries(${PROJECT_NAME} asound)
find_package(asound)

