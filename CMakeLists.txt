cmake_minimum_required(VERSION 3.20.0)
project(planning)

set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin) #windwos平台使用
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LISTS)
add_library(
    common
    SHARED
    ${SRC_LISTS}
)

target_include_directories(
    common
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
)


#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)


add_executable(planning__ planning_main.cpp)

target_include_directories(planning__
PUBLIC
${PROJECT_SOURCE_DIR}/include
)

target_link_libraries(planning__
PUBLIC
common
)