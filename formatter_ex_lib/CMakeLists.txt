cmake_minimum_required(VERSION 3.4)
project(formatter_ex_lib)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(SOURSES ${PROJECT_SOURSE_DIR} ../formatter_lib) # Добавляем источники: текучая директория проекта и директория используемой бибиотеки


add_library(formatter_ex_lib STATIC formatter_ex.cpp formatter_ex.h)

add_subdirectory(../formatter_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_lib)  # Добавляем в сборку директорию предыдущей библиотеки
target_include_directories(formatter_ex_lib PUBLIC ${SOURSES}) 

target_link_libraries(formatter_ex_lib formatter_lib) #Указываем что у нас используется предыдущая библиотека, которую мы добавили в папку build