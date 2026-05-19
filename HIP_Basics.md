# HIP Basics - AMD's Portable GPU Programming Model

## What is HIP?

**HIP** (Heterogeneous-compute Interface for Portability) is AMD's open-source C++ runtime API and kernel language. It is designed to be **very similar to CUDA**, making it easy to port code between NVIDIA and AMD GPUs.

HIP code can run on both AMD GPUs (via ROCm) and NVIDIA GPUs (via hipify + CUDA).

## Key Features

- Almost identical syntax to CUDA
- `hipcc` compiler
- Wavefront size = **64** (vs CUDA Warp size = 32)
- Uses `__global__`, `hipMalloc`, `hipMemcpy`, etc.

## Sample HIP Code

```cpp
// hip_example.cpp
#include <hip/hip_runtime.h>
#include <stdio.h>

__global__ void helloHIP() {
    printf("Hello from AMD GPU! Work-item ID: %d\n", threadIdx.x);
}

int main() {
    helloHIP<<<1, 8>>>();
    hipDeviceSynchronize();
    return 0;
}
```
