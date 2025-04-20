cmake_minimum_required(VERSION 3.10)

project(tetris LANGUAGES C CXX)


set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(vendor/raylib)

file(
    GLOB_RECURSE SRC_FILES
    
    # src/main.cpp
)

add_executable(${PROJECT_NAME} src/main.cpp ${SRC_FILES})

target_link_libraries(${PROJECT_NAME} raylib)

target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    
    ${CMAKE_CURRENT_SOURCE_DIR}/vendor/raylib/src
)
