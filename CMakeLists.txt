cmake_minimum_required(VERSION 3.0)

project(pyreball)

enable_language(Fortran)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

# Compilar programa en Fortran
add_executable(pyreball ${CMAKE_SOURCE_DIR}/src/pyreball.f90 
                        ${CMAKE_SOURCE_DIR}/src/suma.f90
                        ${CMAKE_SOURCE_DIR}/src/variables.f90
                        )

# Generar el módulo compilado con f2py
#add_custom_command(OUTPUT ${CMAKE_SOURCE_DIR}/src/fortran_suma.so
#                   COMMAND f2py -c ${CMAKE_SOURCE_DIR}/src/suma.f90 -m fortran_suma
#                   WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/src
#                   COMMENT "Compilando la subrutina Fortran con f2py"
#                   VERBATIM)
#
#add_custom_target(fortran_suma ALL DEPENDS ${CMAKE_SOURCE_DIR}/src/fortran_suma.so)