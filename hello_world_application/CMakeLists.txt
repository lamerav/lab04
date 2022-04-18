cmake_minimum_required(VERSION 3.4)
project(hello_world)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(SOURSES ${PROJECT_SOURSE_DIR} ../formatter_ex_lib)

add_subdirectory(../formatter_ex_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_ex_lib)

target_include_directories(formatter_ex_lib PUBLIC ${SOURSES}) 
add_executable(example hello_world.cpp) # В данном проекте требуется создать исполняемый файл, а не библитеку.
target_link_libraries(example formatter_ex_lib)