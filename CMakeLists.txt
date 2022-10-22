project(Random_Pokemon_Battle_sim)
cmake_minimum_required(VERSION 3.12)

include(GNUInstallDirs)

# Define which cpp files we want to compile
set(SOURCES 
    Pokemon.cpp
#   otherfile.cpp
#   thirdfile.cpp
)

# Make sure any header files in the current directory are picked up by the compiler
include_directories(
    "."
)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCES})

# Install executable and symbol file (if available)
install(
        FILES $<TARGET_PDB_FILE:${CMAKE_PROJECT_NAME}>
        DESTINATION "${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_BINDIR}"
    )
install(TARGETS ${CMAKE_PROJECT_NAME}
        DESTINATION "${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_BINDIR}")