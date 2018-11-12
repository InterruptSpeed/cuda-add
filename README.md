# cuda-add
work files for the article https://devblogs.nvidia.com/even-easier-introduction-cuda/

```
cl add.cpp /EHSc

nvcc add.cu -o add_cuda.exe
nvcc add_block.cu -o add_block_cuda.exe
nvcc add_grid.cu -o add_grid_cuda.exe

nvprof add_cuda.exe
nvprof add_block_cuda.exe
nvprof add_grid_cuda.exe
```

or this against CUDA 9.2 on Windows 10 due to a message: "Warning: Unified Memory Profiling is not supported on the current configuration because a pair of devices without peer-to-peer support is detected on this multi-GPU setup. When peer mappings are not available, system falls back to using zero-copy memory. It can cause kernels, which access unified memory, to run slower. More details can be found at: http://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html#um-managed-memory"
```
nvprof --unified-memory-profiling off add_cuda.exe
nvprof --unified-memory-profiling off add_block_cuda.exe
nvprof --unified-memory-profiling off add_grid_cuda.exe
```