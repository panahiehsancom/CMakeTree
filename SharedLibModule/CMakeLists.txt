cmake_minimum_required(VERSION 3.5)

add_subdirectory(include)
add_subdirectory(src)


set(Module_Name SharedLibModule)
set(MODULE_INCLUDE_PATH ${Module_Name})

include(${PROJECT_SOURCE_DIR}/CommonCmakeLists.cmake)

add_library(${Module_Name} STATIC ${INCLUDE_LIST} ${SRC_LIST})
add_dependencies(${Module_Name} ${CMAKE_PROJECT_NAME}_build_headers)
 
