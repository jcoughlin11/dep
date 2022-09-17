cmake_minimum_required(VERSION 3.22)


project(dep)


set(CMAKE_VERBOSE ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_BUILD_TYPE RELEASE)




message("Setting dep sources...")
set(
    DEP_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/src/greet.cpp
)

message("Setting dep includes...")
set(
    DEP_INC
    ${CMAKE_CURRENT_SOURCE_DIR}/inc/
)

message("Setting dep install dir...")
set(
    DEP_INSTALL
    $ENV{HOME}/Code/sandbox/cmake/install
)


message("Including dep headers...")
include_directories(${DEP_INC})


# Compilation step
message("Building dep lib...")
add_library(foo SHARED ${DEP_SRC})


message("Installing dep...")
install(
    TARGETS foo
    LIBRARY
    DESTINATION ${DEP_INSTALL} 
)
