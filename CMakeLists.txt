cmake_minimum_required(VERSION 3.0)

project(twitcurl VERSION 1.0 LANGUAGES CXX)

FIND_PACKAGE(PkgConfig)
include_directories (${PKGS_INCLUDE_DIRS})

set(twitSrcs base64.cpp HMAC_SHA1.cpp oauthlib.cpp SHA1.cpp urlencode.cpp twitcurl.cpp)

add_library(twitcurl SHARED ${twitSrcs})

set_target_properties(twitcurl PROPERTIES SOVERSION 1)
set_target_properties(twitcurl PROPERTIES PUBLIC_HEADER twitcurl.h)

set_property(TARGET twitcurl PROPERTY CXX_STANDARD 17)

include(GNUInstallDirs)

configure_file(twitcurl.pc.in twitcurl.pc @ONLY)
install(FILES ${CMAKE_BINARY_DIR}/twitcurl.pc DESTINATION ${CMAKE_INSTALL_DATAROOTDIR}/pkgconfig)

install(TARGETS twitcurl
	LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
