cmake_minimum_required(VERSION 3.5)

project(kf_ca_2d LANGUAGES C)

set(
    SOURCES
    kf_ca_2d.c
)

set(
    HEADERS
    kf_ca_2d.h
)


add_library(kf_ca_2d_static STATIC ${SOURCES} ${HEADERS})
add_library(kf_ca_2d_shared SHARED ${SOURCES} ${HEADERS})

set_target_properties(kf_ca_2d_static PROPERTIES OUTPUT_NAME kf_ca_2d)
set_target_properties(kf_ca_2d_shared PROPERTIES OUTPUT_NAME kf_ca_2d)

target_include_directories(kf_ca_2d_static PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(kf_ca_2d_shared PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

install(TARGETS kf_ca_2d_static DESTINATION lib)
install(TARGETS kf_ca_2d_shared DESTINATION lib)
install(FILES ${HEADERS} DESTINATION include)