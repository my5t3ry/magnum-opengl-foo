cmake_minimum_required(VERSION 3.4)
project(MyApplication)

set(WITH_SDL2APPLICATION ON CACHE BOOL "" FORCE)
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/modules/" ${CMAKE_MODULE_PATH})


set(IMGUI_DIR ${CMAKE_CURRENT_SOURCE_DIR}/imgui)
set(WITH_IMGUI ON CACHE BOOL "" FORCE)
add_subdirectory(magnum-integration EXCLUDE_FROM_ALL)

# Add Corrade as a subproject
add_subdirectory(corrade EXCLUDE_FROM_ALL)

# Add Magnum as a subproject, enable Sdl2Application
add_subdirectory(magnum EXCLUDE_FROM_ALL)

find_package(Magnum REQUIRED)
find_package(MagnumIntegration REQUIRED ImGui)

#add_subdirectory(src)
add_subdirectory(src3)
