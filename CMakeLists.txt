cmake_minimum_required(VERSION 3.21 FATAL_ERROR)

project(hellocmakepro LANGUAGES CXX)

set_property(GLOBAL 
    PROPERTY CXX_STANDARD 20
    PROPERTY CXX_STANDARD_REQUIRED ON)

add_executable(hellocmake main.cpp)

install(TARGETS hellocmake RUNTIME DESTINATION bin)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED IMPORTED_TARGET gtk3)

target_link_libraries(app PRIVATE fmt PkgConfig::GTK3)