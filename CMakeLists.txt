#------------------------------------------------------------------
# CMakeLists.txt
#------------------------------------------------------------------
cmake_minimum_required(VERSION 2.8)


#------------------------------------------------------------------
# Squid project
#------------------------------------------------------------------
project(Squid)


#------------------------------------------------------------------
# project root directory
#------------------------------------------------------------------
set(SQUID_ROOT ${CMAKE_CURRENT_LIST_DIR})


#------------------------------------------------------------------
# output directory
#------------------------------------------------------------------
set(SQUID_ARCHIVE_OUTPUT_DIRECTORY "${SQUID_ROOT}/bin/obj")
set(SQUID_LIBRARY_OUTPUT_DIRECTORY "${SQUID_ROOT}/bin/lib")
set(SQUID_RUNTIME_OUTPUT_DIRECTORY "${SQUID_ROOT}/bin")


#------------------------------------------------------------------
# include directories
#------------------------------------------------------------------
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)


#------------------------------------------------------------------
# add library function
#------------------------------------------------------------------
function(squid_add_library name sources targets)
    add_library(${name} ${sources})
    target_link_libraries(${name} ${targets})
    set_target_properties(
        ${name} PROPERTIES
        ARCHIVE_OUTPUT_DIRECTORY ${SQUID_ARCHIVE_OUTPUT_DIRECTORY}
        LIBRARY_OUTPUT_DIRECTORY ${SQUID_LIBRARY_OUTPUT_DIRECTORY}
        RUNTIME_OUTPUT_DIRECTORY ${SQUID_RUNTIME_OUTPUT_DIRECTORY}
    )
endfunction()


#------------------------------------------------------------------
# add test function
#------------------------------------------------------------------
function(squid_add_test name sources targets)
endfunction()



