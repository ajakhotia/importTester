cmake_minimum_required(VERSION 3.10)

project(importTester VERSION 0.1.0.0)

option(IMPORT_TESTER_FIND_ALL_KNOWN_PROJECTS "Ask importTest to find all packages it is aware of" OFF)

# A convenience macro to setup options for various packages we would like to find using this project
macro(setup_find PACKAGE_NAME)
    option(IMPORT_TESTER_FIND_${PACKAGE_NAME} "Ask import test to find ${PACKAGE_NAME} package" OFF)

    if(IMPORT_TESTER_FIND_${PACKAGE_NAME} OR IMPORT_TESTER_FIND_ALL_KNOWN_PROJECTS)
        message(STATUS "Finding ${PACKAGE_NAME} package")
        find_package(${PACKAGE_NAME} REQUIRED)
    endif()

endmacro()


setup_find(units)
