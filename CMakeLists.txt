cmake_minimum_required(VERSION 2.8)

get_filename_component(PROJECT_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME)

project( ${PROJECT_NAME} CXX )

if(IS_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include)
    list(APPEND PATH_INCLUDES ${CMAKE_CURRENT_SOURCE_DIR})
    FILE (GLOB_RECURSE  HEADERS ${CMAKE_CURRENT_SOURCE_DIR}/include/*)
endif()
include_directories(${PATH_INCLUDES})

FILE (GLOB_RECURSE SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/src/*)

add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS} )