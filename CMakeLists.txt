cmake_minimum_required(VERSION 3.0.2 FATAL_ERROR)

###############################################################################
# 									stb
###############################################################################
# Project name and version
project(stb VERSION 1.0 LANGUAGES C)

# Project options
option(STB_BUILD_TESTS "Build the stb tests" OFF)

# Find the library header files
file(GLOB STB_HEADERS "*.h")

# Create the library
add_library(stb INTERFACE)

target_include_directories(stb INTERFACE
	$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
	$<INSTALL_INTERFACE:include>
)

# Install the library
install(TARGETS stb)
install(FILES ${STB_HEADERS}
	DESTINATION include
)

# Create the tests
if(STB_BUILD_TESTS)
	message(FATAL_ERROR "Tests not implemented yet")
endif()
