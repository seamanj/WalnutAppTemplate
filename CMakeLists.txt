cmake_minimum_required(VERSION 3.10)
project(WalnutAPPTemplate)


add_subdirectory(Walnut)


set(CMAKE_CXX_STANDARD 17)

add_compile_definitions(WL_PLATFORM_WINDOWS)
#file(GLOB_RECURSE src "Walnut/src/*.cpp" "WalnutApp/src/*.cpp")
set(src "WalnutApp/src/WalnutApp.cpp")



set(std_image_dir ${CMAKE_CURRENT_SOURCE_DIR}/vendor/stb_image)
include_directories(${std_image_dir})
include_directories(Walnut/Walnut/src)


add_executable(${PROJECT_NAME} ${src})
target_link_libraries(${PROJECT_NAME} Walnut)
