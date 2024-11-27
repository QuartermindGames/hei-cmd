add_library(
        valve_plugin SHARED
        plugin.c plugin.h
        vtf.c
)
target_compile_definitions(valve_plugin PRIVATE
        PL_COMPILE_PLUGIN)
target_include_directories(valve_plugin PRIVATE
        ../../hei/plcore/include/)

set_target_properties(
        valve_plugin PROPERTIES
        LIBRARY_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../../../bin/plugins/")
