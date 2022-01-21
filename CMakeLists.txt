cmake_minimum_required(VERSION 3.15)

include(cmake_includes/DefineProjectOnce.cmake)
define_project_once(my_app)

project(my_app CXX)

# example conan depends set(CONAN_EXTRA_REQUIRES ${CONAN_EXTRA_REQUIRES}
# "cppzmq/4.8.1") set(CONAN_EXTRA_REQUIRES ${CONAN_EXTRA_REQUIRES} "fmt/8.0.1")

include(cmake_includes/Standalone.cmake)

add_subdirectory(src)
add_subdirectory(external)

if(ENABLE_TESTING)
    # enable_testing() add_subdirectory(test)
endif()

if(RECURSIVE_BUILD_TESTS AND ENABLE_TESTING)
    # A parent project has requested tests. add_subdirectory(test)
endif()

# install(TARGETS sv DESTINATION bin)
