project(OneDMin Fortran)
cmake_minimum_required(VERSION 2.8)

find_package(BLAS REQUIRED)
find_package(LAPACK REQUIRED)
message(STATUS "Found BLAS: ${BLAS_LIBRARIES}")
message(STATUS "Found LAPACK: ${LAPACK_LIBRARIES}")

set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -Wall -g")

add_library(ljlibs
    ${PROJECT_SOURCE_DIR}/src/mass.f
    ${PROJECT_SOURCE_DIR}/src/spin.f)

add_library(exp6libs
    ${PROJECT_SOURCE_DIR}/src/exp6.f)
add_library(ddmolprolibs
    ${PROJECT_SOURCE_DIR}/src/dd-molpro.f)
add_library(ddgaussianlibs
    ${PROJECT_SOURCE_DIR}/src/dd-gaussian.f)

add_executable(onedmin-exp6.x
    ${PROJECT_SOURCE_DIR}/src/onedmin.f)
target_link_libraries(onedmin-exp6.x 
    ${BLAS_LIBRARIES} ${LAPACK_LIBRARIES} ljlibs exp6libs)

add_executable(onedmin-dd-molpro.x
    ${PROJECT_SOURCE_DIR}/src/onedmin.f)
target_link_libraries(onedmin-dd-molpro.x 
    ${BLAS_LIBRARIES} ${LAPACK_LIBRARIES} ljlibs ddmolprolibs)

add_executable(onedmin-dd-gaussian.x
    ${PROJECT_SOURCE_DIR}/src/onedmin.f)
target_link_libraries(onedmin-dd-gaussian.x 
    ${BLAS_LIBRARIES} ${LAPACK_LIBRARIES} ljlibs ddgaussianlibs)

install(TARGETS onedmin-exp6.x DESTINATION bin)
install(TARGETS onedmin-dd-molpro.x DESTINATION bin)
install(TARGETS onedmin-dd-gaussian.x DESTINATION bin)
