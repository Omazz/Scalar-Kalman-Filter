cmake_minimum_required(VERSION 3.5)

project(kf_cv_1d LANGUAGES C)

set(
    SOURCES
    kf_cv_1d.c
)

set(
    HEADERS
    kf_cv_1d.h
)


add_library(kf_cv_1d_static STATIC ${SOURCES} ${HEADERS})
add_library(kf_cv_1d_shared SHARED ${SOURCES} ${HEADERS})

set_target_properties(kf_cv_1d_static PROPERTIES OUTPUT_NAME kf_cv_1d)
set_target_properties(kf_cv_1d_shared PROPERTIES OUTPUT_NAME kf_cv_1d)

target_include_directories(kf_cv_1d_static PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(kf_cv_1d_shared PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

install(TARGETS kf_cv_1d_static DESTINATION lib)
install(TARGETS kf_cv_1d_shared DESTINATION lib)
install(FILES ${HEADERS} DESTINATION include)