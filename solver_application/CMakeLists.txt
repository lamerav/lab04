cmake_minimum_required(VERSION 3.4)
project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(SOURSES ${PROJECT_SOURSE_DIR} ../formatter_ex_lib ../solver_lib)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib ${CMAKE_CURRENT_BINARY_DIR}/solver)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter)

add_executable(example equation.cpp)
target_include_directories(example PUBLIC ${SOURSES})

target_link_libraries(example solver_lib formatter_ex_lib)