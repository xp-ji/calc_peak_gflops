CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

PROJECT(calc_peak_gflops)

FIND_PACKAGE(CUDA REQUIRED)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
SET(CUDA_NVCC_FLAGS ${CUDA_NVCC_FLAGS};-gencode arch=compute_61,code=sm_61;-std=c++11;)


INCLUDE_DIRECTORIES(
    /usr/local/cuda/include
)
LINK_DIRECTORIES(
    /usr/local/cuda/lib64
)

CUDA_ADD_EXECUTABLE(calc_peak_gflops
    main.cpp
)
