# CMakeLists.txt
#
# Simple CMake Template for creating temporary MSVC projects 
# (i.e. for tutorials, etc.)
# 
# MIT License
#
# Copyright (c) 2023 Johann Horvat
# 
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
# 
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

cmake_minimum_required(VERSION 3.6)

get_filename_component(ProjectId ${CMAKE_CURRENT_SOURCE_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})
project(Vulkan-Tutorial-${ProjectId})

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# add your include directories here ...
include_directories(
    #"C:/gSomeDirectoryit/Vulkan.latest/Include" 
    #"C:/SomeDirectory/glm"
    #"C:/SomeDirectory/glfw-3.3.8.bin.WIN64/include"
)

if(MSVC)
    SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /ENTRY:mainCRTStartup")
endif()

set (
    PROJECT_SOURCE_FILES
    main.cpp
)

# add your library directories here ...
link_directories(
    #"C:/SomeDirectory/Vulkan.latest/Lib"
    #"C:/SomeDirectory/glfw-3.3.8.bin.WIN64/lib-vc2019"
)

add_executable(${PROJECT_NAME} ${PROJECT_SOURCE_FILES})

# add your libraries here
target_link_libraries(
    ${PROJECT_NAME}
    #"vulkan-1.lib"
    #"glfw3.lib"
)

if(MSVC)
    set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT ${PROJECT_NAME})
endif()
