cmake_minimum_required(VERSION 3.5)
project(boost_di_vendor)

find_package(ament_cmake REQUIRED)

include(ExternalProject)

ExternalProject_Add(boost_di
  PREFIX boost_di
  GIT_REPOSITORY https://github.com/boost-ext/di.git
  GIT_TAG cpp14
  CMAKE_ARGS
   -DCMAKE_INSTALL_PREFIX=${CMAKE_CURRENT_BINARY_DIR}/boost_di_install
  INSTALL_DIR "${CMAKE_CURRENT_BINARY_DIR}/boost_di_install"
)
install (DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/boost_di_install DESTINATION ${CMAKE_INSTALL_PREFIX})

ament_package()