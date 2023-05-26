CC=nvcc
CUDACC=nvcc

#CCFLAGS= -g -O3 -std=c++11 -Wall
CUDACFLAGS= -O3 -std=c++11 -I${NCAR_ROOT_CUDA} -arch sm_75
CUDALDFLAGS= -L${CUDA_ROOT_PATH}/lib64 -lcudart


BINARY=fma_tensor

all: $(BINARY)

$(BINARY): fma_tensor.o
	$(CC) -o $(BINARY) fma_tensor.o
	
fma_tensor.o: fma_tensor.cu
	$(CUDACC) -c $(CUDACFLAGS) fma_tensor.cu

clean: 
	rm *.o $(BINARY)
