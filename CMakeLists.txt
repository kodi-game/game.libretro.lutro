cmake_minimum_required(VERSION 3.1)
project(game.libretro.lutro)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(LUTRO_LIB NAMES lutro_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(LUTRO_CUSTOM_BINARY ${LUTRO_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} LUTRO "")

include(CPack)
