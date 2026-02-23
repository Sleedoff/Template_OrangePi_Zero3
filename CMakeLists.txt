cmake_minimum_required(VERSION 3.18)
project(template_orange_pi_zero3)

add_subdirectory(Periphery_OrangePi_Zero3)

set(SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(INCLUDE 
    ${SOURCE_DIR}/Main/Include/main.h
    ${SOURCE_DIR}/Main/Include/startup.h)

set(SOURCE
    ${SOURCE_DIR}/Main/Source/main.cpp
    ${SOURCE_DIR}/Main/Source/startup.cpp)

add_executable(${PROJECT_NAME} ${SOURCE})

include_directories(${SOURCE_DIR}/Main/Source
                    ${SOURCE_DIR}/Main/Include
)

target_link_libraries(${PROJECT_NAME} PRIVATE
    periphery_lib
)