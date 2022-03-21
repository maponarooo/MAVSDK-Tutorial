cmake_minimum_required(VERSION 3.10.2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(getsystem)

add_executable(getsystem
   getsystem.cpp
)

find_package(MAVSDK REQUIRED)

target_link_libraries(getsystem
    MAVSDK::mavsdk
)

if(NOT MSVC)
    add_compile_options(takeoff_and_land PRIVATE -Wall -Wextra)
else()
    add_compile_options(takeoff_and_land PRIVATE -WX -W2)
endif()
