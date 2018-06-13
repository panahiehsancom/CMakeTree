cmake_minimum_required(VERSION 3.5)

add_subdirectory(include)
add_subdirectory(src)

set(Module_Name GUI)
set(MODULE_INCLUDE_PATH ${Module_Name})

include(${PROJECT_SOURCE_DIR}/CommonCmakeLists.cmake)




add_library(${Module_Name} STATIC ${SRC_LIST}  ${INCLUDE_LIST})



target_link_libraries(${Module_Name} SharedLibModule)

add_dependencies(${Module_Name} ${CMAKE_PROJECT_NAME}_build_headers)

