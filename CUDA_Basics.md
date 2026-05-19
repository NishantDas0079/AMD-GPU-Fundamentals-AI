# CUDA Basics - NVIDIA's GPU Programming Model

## What is CUDA?

**CUDA** (Compute Unified Device Architecture) is NVIDIA's proprietary parallel computing platform and programming model. It allows developers to write C/C++ code that runs directly on NVIDIA GPUs.

Released in 2007, CUDA revolutionized GPGPU (General Purpose GPU) computing by letting programmers use familiar C/C++ syntax instead of graphics APIs.

## Key Concepts

- **Kernel**: Function that runs on the GPU
- **Thread**: Smallest unit of execution
- **Block**: Group of threads (up to 1024)
- **Grid**: Group of blocks
- **Warp**: Group of 32 threads executed together (SIMT)

## Sample CUDA Code

```cuda
// cuda_example.cu
#include <stdio.h>

__global__ void helloCUDA() {
    printf("Hello from GPU! Thread ID: %d\n", threadIdx.x);
}

int main() {
    helloCUDA<<<1, 8>>>();
    cudaDeviceSynchronize();
    return 0;
}
```
