cmake_minimum_required(VERSION 3.21 FATAL_ERROR)

project(hellocmakepro LANGUAGES CXX)

add_executable(hellocmake main.cpp)

install(TARGETS hellocmake RUNTIME DESTINATION bin)
