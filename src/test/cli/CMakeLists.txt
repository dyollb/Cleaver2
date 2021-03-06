########################################################################

# Tests for cli
include_directories(${CLEAVER2_SOURCE_DIR}/lib/gtest)
include_directories(${CLEAVER2_SOURCE_DIR}/lib/gtest/include)
add_definitions(-DBINARY_DIR="${CLEAVER2_BINARY_DIR}/bin/")
add_definitions(-DTEST_DATA_DIR="${CLEAVER2_SOURCE_DIR}/test/test_data/")
#cli
cxx_test(cli_basic gtest_main cli_common.cc)
cxx_test(cli_scale gtest_main cli_common.cc)
cxx_test(cli_alpha gtest_main cli_common.cc)
cxx_test(cli_padding gtest_main cli_common.cc)
cxx_test(cli_regular gtest_main cli_common.cc)
cxx_test(cli_short gtest_main cli_common.cc)
cxx_test(cli_long gtest_main cli_common.cc)
cxx_test(cli_strict gtest_main cli_common.cc)
cxx_test(cli_background gtest_main cli_common.cc)
cxx_test(cli_sizing gtest_main cli_common.cc)
cxx_test(cli_grading gtest_main cli_common.cc)
cxx_test(cli_multiplier gtest_main cli_common.cc)
cxx_test(cli_strip gtest_main cli_common.cc)
cxx_test(cli_vtk gtest_main cli_common.cc)
cxx_test(cli_jacobian gtest_main cli_common.cc)
cxx_test(cli_scirun gtest_main cli_common.cc)
cxx_test(cli_matlab gtest_main cli_common.cc)
#only build this if the tools exist. Windows has a slightly different result, 
#so this test will just fail, and will be excluded on WIN32
if (USE_SEGMENTATION_TOOLS AND NOT WIN32)
	cxx_test(cli_segmentation gtest_main cli_common.cc)
endif()
