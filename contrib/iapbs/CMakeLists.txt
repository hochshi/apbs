################################################################################
# Set up basic project stuff                                                   #
################################################################################
cmake_minimum_required(VERSION 3.6)

include(CheckIncludeFiles)
include(CheckFunctionExists)
include(CheckSymbolExists)
include(CheckTypeSize)
include(ExternalProject)

set(iAPBS_VERSION "3.2.0")

PROJECT(iAPBS)
################################################################################
# Set project paths                                                            #
################################################################################

message(STATUS "Setting iAPBS project paths")
set(iAPBS_ROOT ${PROJECT_SOURCE_DIR})


################################################################################
# add src
################################################################################


add_subdirectory(src)

#get_cmake_property(_variableNames VARIABLES)
#foreach (_variableName ${_variableNames})
#    message(STATUS "${_variableName}=${${_variableName}}")
#endforeach()
