cmake_minimum_required(VERSION 3.22)


project(dep)


set(CMAKE_VERBOSE ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_BUILD_TYPE RELEASE)




set(
    DEP_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/src/greet.cpp
)

set(
    DEP_INC
    ${CMAKE_CURRENT_SOURCE_DIR}/inc/
)

set(
    DEP_INSTALL
    $ENV{HOME}/.dephy/lib
)



include_directories(${DEP_INC})


# Compilation step
add_library(foo SHARED ${DEP_SRC})


install(
    TARGETS foo
    LIBRARY
    DESTINATION ${DEP_INSTALL} 
)
