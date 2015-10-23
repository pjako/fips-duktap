#
# project: fips-duktape
#

if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup()
    fips_project(fips-duktape)
endif()

fips_begin_lib(duktape)
    fips_files(duktape.c duktape.h duk_config.h)
fips_end_lib()

if (NOT FIPS_IMPORT)
    fips_finish()
endif()