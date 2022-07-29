cmake_minimum_required(VERSION 3.21)
project("liba53" VERSION 1.0)

set(LIBA53_SOURCE_FILES a5.c bits.c gea.c kasumi.c utils.c ifc.cpp)
set(LIBA53_INCLUDE_FILES a5.h bits.h gea.h gprs_cipher.h kasumi.h linuxlist.h utils.h)

add_library(a53 SHARED ${LIBA53_SOURCE_FILES})
target_include_directories(a53 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
set_target_properties(a53 PROPERTIES
    VERSION ${PROJECT_VERSION}
    SOVERSION ${PROJECT_VERSION_MAJOR}
    PUBLIC_HEADER "a53.h"
    POSITION_INDEPENDENT_CODE ON
)

include(GNUInstallDirs)
install(TARGETS a53
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
)

enable_testing()

add_executable(a53test a53test.cpp)
target_link_libraries(a53test PRIVATE a53)

add_test(NAME "a53test" COMMAND a53test)
