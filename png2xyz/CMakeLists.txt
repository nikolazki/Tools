cmake_minimum_required(VERSION 3.7)
project(png2xyz VERSION 1.0 LANGUAGES CXX)

set(CMAKE_MODULE_PATH APPEND "${CMAKE_CURRENT_SOURCE_DIR}/../Modules")

include(ConfigureWindows)

find_package(PNG REQUIRED)

add_executable(png2xyz src/png2xyz.cpp)

target_link_libraries(png2xyz PNG::PNG)

include(GNUInstallDirs)
install(TARGETS png2xyz RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
