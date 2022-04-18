cmake_minimum_required(VERSION 3.4) # Необходимая минимальная версия cmake
project(formatter_lib)              # Имя проекта

set(CMAKE_CXX_STANDARD 11)          # Версия С++
set(CMAKE_CXX_STANDARD_REQUIRED ON) # Включаем требование к стандарту C++

add_library(formatter_lib STATIC formatter.cpp formatter.h) # Создание статической библиотеки

target_include_directories(formatter_lib PUBLIC ${PROJECT_SOURSE_DIR})  # Указываем cmake где искать заголовочные файлы для библиотеки formatter_lib