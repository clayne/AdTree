cmake_minimum_required(VERSION 3.12)

get_filename_component(MODULE_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME)
set(PROJECT_NAME easy3d_${MODULE_NAME})
project(${PROJECT_NAME})


set(${PROJECT_NAME}_HEADERS
    box.h
    constant.h
    eigen_solver.h
    graph.h
    line.h
    mat.h
    plane.h
    point_cloud.h
    principal_axes.h
    properties.h
    quat.h
    random.h
    rect.h
    segment.h
    surface_mesh.h
    types.h
    vec.h
    )

set(${PROJECT_NAME}_SOURCES
    graph.cpp
    point_cloud.cpp
    surface_mesh.cpp
    )

	
add_library(${PROJECT_NAME} STATIC ${${PROJECT_NAME}_SOURCES} ${${PROJECT_NAME}_HEADERS} )

set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER "3rd_party/easy3d")

target_include_directories(${PROJECT_NAME} PRIVATE ${ADTREE_easy3d_INCLUDE_DIR})


