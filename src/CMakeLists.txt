add_subdirectory(memory)
add_subdirectory(type)
add_subdirectory(util)


# add_libray must have files
add_library(koishidb STATIC ${ALL_OBJECT_FILES})

# target_link_libraries
target_link_libraries(koishidb
        koishidb_memory
        koishidb_type
        koishidb_util
        )
target_include_directories(koishidb PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)

add_executable(main main.cc)
target_link_libraries(main koishidb)