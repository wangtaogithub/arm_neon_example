project(leetcode)

set(CMAKE_VERBOSE_MAKEFILE on)

#build vmovq_n_u8 with and without neon instructtion, like: movi v0.16b, #0x3
add_compile_options(-Wall -march=armv8-a)

add_executable(vmovq_n_u8.out vmovq_n_u8.c)
add_executable(vmovq_n_u8_no_neon.out vmovq_n_u8.c)
add_executable(matrix_add_number.out matrix_add_number.c)
add_executable(matrix_add_number_no_neon.out matrix_add_number.c)
add_executable(vld1q_u8.out vld1q_u8.c)
add_executable(vld1q_u8_no_neon.out vld1q_u8.c)


target_compile_options(vmovq_n_u8.out PRIVATE -O3)
#target_compile_options(vmovq_n_u8_no_neon.out PRIVATE -O0)
target_compile_options(matrix_add_number.out PRIVATE -O3)
#target_compile_options(matrix_add_number_no_neon.out PRIVATE -O0)
target_compile_options(vld1q_u8.out PRIVATE -O3)
#target_compile_options(vld1q_u8_no_neon.out PRIVATE -O0)


add_executable(arm_neon_add.out arm_neon_add.c)
cmake_minimum_required(VERSION 2.8.0)
