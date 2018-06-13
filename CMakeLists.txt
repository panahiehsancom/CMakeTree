cmake_minimum_required(VERSION 3.5)
project(CMakeTree C CXX)

include_directories(${CMAKE_BINARY_DIR}/include/)
add_custom_target(${CMAKE_PROJECT_NAME}_build_headers)

add_subdirectory(SharedLibModule)
add_subdirectory(ModuleB)
add_subdirectory(GUIModuleA)
add_subdirectory(ModuleC)
add_subdirectory(ModuleD)
add_subdirectory(ModuleE)

add_subdirectory(include)
add_subdirectory(src)


include(CommonCmakeLists.cmake)



add_executable(${PROJECT_NAME}  include/${INCLUDE_LIST} src/${SRC_LIST})

set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)

target_link_libraries(${PROJECT_NAME}  ModuleB ModuleC ModuleD ModuleE)

