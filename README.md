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