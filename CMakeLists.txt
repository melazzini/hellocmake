cmake_minimum_required(VERSION 3.21 FATAL_ERROR)

project(hellocmakepro LANGUAGES CXX)

set_property(GLOBAL 
    PROPERTY CXX_STANDARD 20
    PROPERTY CXX_STANDARD_REQUIRED ON)

add_executable(hellocmake main.cpp)

install(TARGETS hellocmake RUNTIME DESTINATION bin)

find_package(PkgConfig REQUIRED)
pkg_check_modules(gtk3 REQUIRED IMPORTED_TARGET gtk+-3.0)
pkg_search_module(gstreamer REQUIRED IMPORTED_TARGET gstreamer-1.0)
# pkg_search_module(gstreamer-sdp REQUIRED IMPORTED_TARGET gstreamer-sdp-1.0)
# pkg_search_module(gstreamer-app REQUIRED IMPORTED_TARGET gstreamer-app-1.0>=1.4)
# pkg_search_module(gstreamer-video REQUIRED IMPORTED_TARGET gstreamer-video-1.0>=1.4)
# add_executable(hellocmake main.cpp)
target_link_libraries(hellocmake
    PkgConfig::gtk3
    PkgConfig::gstreamer
    # PkgConfig::gstreamer-sdp
    # PkgConfig::gstreamer-app
    # PkgConfig::gstreamer-video
)