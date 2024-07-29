cmake_minimum_required(VERSION 3.2)

if("${CMAKE_BUILD_TYPE}" STREQUAL "")
    message(STATUS "CMAKE_BUILD_TYPE is unset, defaulting to Release")
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING
        "Choose the type of build, options are: None Debug Release RelWithDebInfo MinSizeRel RelWithAssert RelWithMDd...")
endif()

set(PROJECT_NAME "example_1")
set(PROJECT_FULL_NAME "Study oneAPI Deep Neural Network Library (oneDNN)")
set(PROJECT_VERSION "1.0.0.0")

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/../3rd/xbyak/build/install/include)

AUX_SOURCE_DIRECTORY(${CMAKE_CURRENT_SOURCE_DIR} SRC_FILES)
ADD_EXECUTABLE(${PROJECT_NAME} ${HEADER_FILES} ${SRC_FILES})