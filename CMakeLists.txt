#
#  Copyright (c) 2013, PAL Robotics, S.L. Author: Karsten Knese
#  Copyright 2010 CNRS
#

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

INCLUDE(cmake/base.cmake)
INCLUDE(cmake/boost.cmake)
INCLUDE(cmake/lapack.cmake)
INCLUDE(cmake/cpack.cmake)

SET(PROJECT_NAME task_joint_limit_clamping)
project(${PROJECT_NAME})

SET(PROJECT_VERSION 1.0)
SET(PROJECT_DESCRIPTION "Task Joint Limit Clamping")
SET(PROJECT_URL "http://")

SET(${PROJECT_NAME}_HEADERS
    include/sot-dyninv/TaskJointLimitClamping.hh
)
#
# Look for dependencies
#

SETUP_PROJECT()


#
#  Documentation dependency to package dynamic-graph
#

# Search for dependencies.
ADD_REQUIRED_DEPENDENCY("jrl-mathtools")
ADD_REQUIRED_DEPENDENCY("jrl-mal")
ADD_REQUIRED_DEPENDENCY("dynamic-graph")
ADD_REQUIRED_DEPENDENCY("dynamic-graph-python")
ADD_REQUIRED_DEPENDENCY("sot-core")

ADD_SUBDIRECTORY(src)

SETUP_PROJECT_FINALIZE()
