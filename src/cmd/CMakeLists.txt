add_executable(hei-cmd
        cmd_main.c

        ../hei/extras/asa/asa.c
        ../hei/extras/asa/asa_format_tre.c
        ../hei/extras/aitd/aitd_pak.c
        ../hei/extras/eradicator_rid.c
        ../hei/extras/package/package_ftactics_pak.c
        ../hei/extras/package/package_haven_dat.c
        ../hei/extras/istorm_ibf.c
        ../hei/extras/outwars_ff.c
        ../hei/extras/package/package_rof.c
        ../hei/extras/sentient_vsr.c
        ../hei/extras/pl_extra_okre.c
        ../hei/extras/pl_extra_kri_wad.c
)

add_dependencies(hei-cmd blitz_plugin core_plugin)

target_include_directories(hei-cmd PRIVATE ../hei/extras)
target_link_libraries(hei-cmd plcore plgraphics plmodel)
