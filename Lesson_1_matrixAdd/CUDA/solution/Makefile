#compilers
CC=nvc++
CUDACC=nvcc

#compilation flags
CFLAGS= -g -O3 -Wall -std=c++11 -I./pch.h
CUDACFLAGS= -g -O3 -std=c++11 -I${CUDA_ROOT_PATH}/include

#linking flags 
LDFLAGS=
CUDALDFLAGS= -L${CUDA_ROOT_PATH}/lib64 -lcudart

BINARY= matrix_add

all: $(BINARY)

$(BINARY): common.o main.o functions.o matrix_add.o
	$(CC) -o $(BINARY) common.o main.o functions.o matrix_add.o $(LDFLAGS) $(CUDALDFLAGS)

#common.o: common.cpp
#	$(CC) -c $(CFLAGS) common.cpp

#functions.o: functions.cpp
#	$(CC) -c $(CFLAGS) functions.cpp

#matrix_add.o: matrix_add.cu
#	$(CUDACC) -c $(CUDACFLAGS) matrix_add.cu

#or simply do
%.o: %.cpp 
	$(CC) -c $(CFLAGS) $<

%.o: %.cu 
	$(CUDACC) -c $(CUDACFLAGS) $<

clean: 
	rm *.o $(BINARY)
