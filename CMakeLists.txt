cmake_minimum_required(VERSION 3.12)
project(sound_effects)

set(CMAKE_CXX_STANDARD 14)

add_executable(${PROJECT_NAME} main.cpp)

INCLUDE(FindPkgConfig)

PKG_SEARCH_MODULE(SDL2 REQUIRED sdl2)
PKG_SEARCH_MODULE(SDL2IMAGE REQUIRED SDL2_image>=2.0.0)
PKG_SEARCH_MODULE(SDL2TTF REQUIRED SDL2_ttf)
PKG_SEARCH_MODULE(SDL2MIXER REQUIRED SDL2_mixer)

INCLUDE_DIRECTORIES(${SDL2_INCLUDE_DIRS} ${SDL2IMAGE_INCLUDE_DIRS} ${SDL2TTF_INCLUDE_DIRS} ${SDL2MIXER_INCLUDE_DIRS})
TARGET_LINK_LIBRARIES(${PROJECT_NAME} ${SDL2IMAGE_LIBRARIES} ${SDL2_LIBRARIES} ${SDL2TTF_LIBRARIES} ${SDL2MIXER_LIBRARIES})

configure_file(prompt.png prompt.png COPYONLY)
configure_file(beat.wav beat.wav COPYONLY)
configure_file(high.wav high.wav COPYONLY)
configure_file(low.wav low.wav COPYONLY)
configure_file(medium.wav medium.wav COPYONLY)
configure_file(scratch.wav scratch.wav COPYONLY)