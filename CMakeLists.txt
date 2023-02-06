cmake_minimum_required(VERSION 3.5)
project(boost_di_vendor)

find_package(ament_cmake REQUIRED)

include(FetchContent)
set(FETCHCONTENT_QUIET OFF)

set(BOOST_DI_OPT_BUILD_TESTS OFF CACHE BOOL "Build tests" FORCE)
set(BOOST_DI_OPT_BUILD_EXAMPLES OFF CACHE BOOL "Build examples" FORCE)

FetchContent_Declare(
        DI
        GIT_REPOSITORY https://github.com/boost-ext/di
        GIT_TAG v1.2.0
)
FetchContent_MakeAvailable(DI)

ament_package()