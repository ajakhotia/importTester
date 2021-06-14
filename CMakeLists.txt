cmake_minimum_required(VERSION 3.10)

project(importTester VERSION 0.1.0.0)

set(IMPORT_TESTER_PACKAGE_LIST "" CACHE STRING "A semi-colon delimited case sensitive list of packages to be found")

foreach(PACKAGE_NAME ${IMPORT_TESTER_PACKAGE_LIST})
    message(STATUS "Finding ${PACKAGE_NAME}")
    find_package(${PACKAGE_NAME} REQUIRED)
endforeach()