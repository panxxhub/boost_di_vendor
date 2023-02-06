cmake_minimum_required(VERSION 3.5)
project(boost_di_vendor)

find_package(ament_cmake REQUIRED)

include(ExternalProject)

ExternalProject_Add(boost_di
        PREFIX boost_di
        GIT_REPOSITORY https://github.com/boost-ext/di
        GIT_TAG v1.2.0
        CMAKE_ARGS
         -DBOOST_DI_OPT_BUILD_TESTS=OFF
         -DBOOST_DI_OPT_BUILD_EXAMPLES=OFF
        INSTALL_COMMAND cmake -E echo "Skipping install step."
)

install(DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/boost_di/src/boost_di/include
        DESTINATION include
)
# export include dir
ament_export_include_directories(include)

ament_package()