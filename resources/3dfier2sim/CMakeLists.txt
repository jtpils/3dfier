cmake_minimum_required (VERSION 3.2)
project (3dfier2sim)

set(CMAKE_CXX_COMPILER g++)
set(CMAKE_CXX_FLAGS "-Wall -std=c++11")

set(${PROJECT_NAME}_VERSION_MAJOR 1)
set(${PROJECT_NAME}_VERSION_MINOR 0)

find_package(CGAL QUIET COMPONENTS Core )

if ( CGAL_FOUND )
  include( ${CGAL_USE_FILE} )
  include( CGAL_CreateSingleSourceCGALProgram )
  create_single_source_cgal_program( "3dfier2sim.cpp" )
else()
  message(STATUS "This program requires the CGAL library, and will not be compiled.")
endif()

