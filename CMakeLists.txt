cmake_minimum_required(VERSION 2.8)
project(DDConvexHull)

set(devkit_base "" CACHE PATH "Location of the devkit")

if(devkit_base STREQUAL "")
    message(FATAL_ERROR "devkit_base not set. Please provide the location of the devkitBase directory.")
endif()

include(${devkit_base}/cmake/pluginEntry.cmake)

set(SOURCE_FILES
    DDConvexHullCmd.cpp
    DDConvexHullNode.cpp
    DDConvexHullPlugin.cpp
    DDConvexHullUtils.cpp
    StanHull/hull.cpp
    StanHull/stanhull.cpp
    StanHull/wavefront.cpp
)

set(HEADER_FILES
    DDConvexHullCmd.h
    DDConvexHullNode.h
    DDConvexHullUtils.h
    StanHull/hull.h
    StanHull/wavefront.h
)

set(LIBRARIES
    OpenMaya
    OpenMayaUI
    OpenMayaRender
    OpenMayaAnim
    Foundation
)

build_plugin()
