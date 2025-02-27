
#SET(APBS_AUX_PATH ${APBS_SRC_PATH}/src/CMakeFiles/apbs.dir)
#Removed ${APBS_INST_PATH}/include from INCLUDE_DIRECTORIES,
#       because it doesn't exist

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR} ${APBS_ROOT}/src)
LINK_DIRECTORIES(${APBS_ROOT_PATH}/lib)

#ADD_LIBRARY(iapbs SHARED apbs_driver.c apbs_driver.h)
ADD_LIBRARY(iapbs apbs_driver.c apbs_driver.h)
target_link_libraries(iapbs ${APBS_LIBS} ${APBS_INTERNAL_LIBS})

option(BUILD_iAPBS_FORTRAN_WRAPPER "Optionally build iAPBS Fortran wrapper" OFF)
if(BUILD_iAPBS_FORTRAN_WRAPPER)

   MESSAGE(STATUS "Building of iAPBS Fortran wrapper enabled")

   ENABLE_LANGUAGE(Fortran)
   ADD_EXECUTABLE(wrapper wrapper.f)
   TARGET_LINK_LIBRARIES(wrapper 
     iapbs
     apbs_routines
     apbs_mg
     apbs_generic
     apbs_pmgc)
   INSTALL(TARGETS wrapper DESTINATION ${CMAKE_INSTALL_BINDIR} COMPONENT executables)
endif()

INSTALL(TARGETS iapbs DESTINATION ${CMAKE_INSTALL_LIBDIR} COMPONENT libraries)

install(FILES apbs_driver.h DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/iapbs COMPONENT headers)
