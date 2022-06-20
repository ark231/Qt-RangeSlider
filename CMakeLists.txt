cmake_minimum_required(VERSION 3.5)

project(Qt_RangeSlider LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Widgets)

add_library(RangeSlider
    RangeSlider.cpp
)

target_link_libraries(RangeSlider PRIVATE
    Qt6::Widgets
)

target_compile_definitions(RangeSlider PRIVATE $<$<NOT:$<CONFIG:Debug>>:QT_NO_DEBUG_OUTPUT$<SEMICOLON>QT_NO_DEBUG>)
