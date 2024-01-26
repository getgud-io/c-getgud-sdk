cmake_minimum_required(VERSION 3.18) # or whatever is suitable/available for you

include(CMakePrintHelpers)

project(
  GetgudSDK_Starter
  VERSION 0.1
  DESCRIPTION "The GetGud REST API SDK"
  LANGUAGES C)

set(CMAKE_SUPPRESS_REGENERATION true)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build/)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build/)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build/)

set(SDK_DIR ${CMAKE_BINARY_DIR}/../../../build/_build/)
link_directories(
  ${SDK_DIR}
)

add_executable(GetgudSDK_Starter main.c)

target_include_directories(GetgudSDK_Starter
		PRIVATE
		../../include/
)

target_link_libraries(GetgudSDK_Starter 
  PUBLIC
  libGetgudSDK.so
)
