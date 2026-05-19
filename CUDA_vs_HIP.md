# CUDA vs HIP - A Complete Comparison

| Feature                  | CUDA (NVIDIA)              | HIP (AMD)                      | Notes |
|-------------------------|---------------------------|-------------------------------|-------|
| Language                | CUDA C++                  | HIP C++ (CUDA-like)           | HIP is designed for portability |
| Compiler                | `nvcc`                    | `hipcc`                       | hipcc can target both |
| Thread Group            | Warp (32 threads)         | Wavefront (64 work-items)     | Important for divergence |
| Memory Allocation       | `cudaMalloc`              | `hipMalloc`                   | Almost identical |
| Kernel Launch           | `<<<grid, block>>>`       | `<<<grid, block>>>`           | Same syntax |
| Shared Memory           | `__shared__`              | `__shared__` (LDS)            | Same keyword |
| Portability             | NVIDIA only               | AMD + NVIDIA (via hipify)     | HIP's biggest strength |
| Maturity                | Very mature               | Growing rapidly               | CUDA still leads in ecosystem |

### When to Use Which?

- **Use CUDA** if targeting only NVIDIA GPUs (best performance & ecosystem).
- **Use HIP** if you want **portability** across AMD + NVIDIA or want to support AMD Instinct GPUs.

### Conversion Tool

AMD provides **`hipify-perl`** and **`hipify-clang`** to automatically convert CUDA code to HIP.

---

