# SPDX-License-Identifier: GPL-3.0-only
# Copyright (c) 2026 wentywenty

cmake_minimum_required(VERSION 3.22)

find_package(soem CONFIG QUIET)

if(TARGET soem)
    message(STATUS "soem-deb: using system-installed SOEM")
else()
    message(STATUS "soem-deb: building SOEM from bundled source")
    set(SOEM_BUILD_SAMPLES OFF CACHE BOOL "" FORCE)
    add_subdirectory(SOEM)
endif()
