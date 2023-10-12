cmake_minimum_required(VERSION 3.22)
project(sundials_test)
add_executable(sundials_test test.cpp)
find_package(SUNDIALS CONFIG REQUIRED)
get_target_property(SUNDIALS_KLU_LIBRARY_LOC SUNDIALS::KLU IMPORTED_LOCATION)
get_target_property(SUNDIALS_KLU_LIBRARY_DIR SUNDIALS::KLU INTERFACE_INCLUDE_DIRECTORIES)
get_target_property(SUNDIALS_KLU_LIBRARY_LIB SUNDIALS::KLU INTERFACE_LINK_LIBRARIES)
message("sundials klu ${SUNDIALS_KLU_LIBRARY_LOC} ${SUNDIALS_KLU_LIBRARY_DIR} ${SUNDIALS_KLU_LIBRARY_LIB}")
message("sundials ${SUNDIALS_INCLUDE_DIR} ${SUNDIALS_LIBRARIES}")
target_link_libraries(sundials_test PRIVATE SUNDIALS::idas SUNDIALS::sunlinsolklu)

# find_package(SUNDIALS CONFIG REQUIRED)
# note: 27 additional targets are not displayed.
# target_link_libraries(main PRIVATE SUNDIALS::KLU SUNDIALS::HYPRE SUNDIALS::MAGMA SUNDIALS::PETSC)