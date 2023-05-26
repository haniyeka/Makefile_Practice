CC=nvc++
CFLAGS= -g -O3 -Wall -std=c++11

ifeq ($(_OpenACC),true)
ACCFLAGS= -acc -gpu=cc60,cc70,managed -Minfo=all -I${NVHPC_ROOT_PATH}/include 
else
ACCFLAGS=
endif

OBJECTS= common.o functions.o main.o matrix_add.o
BINARY= matrix_add


all: $(BINARY) 

$(BINARY): $(OBJECTS)
	$(CC) -o $(BINARY) $(OBJECTS) $(ACCFLAGS)

%.o: %.cpp
	$(CC) -c $(CFLAGS) $(ACCFLAGS) $<

%.o: %.cc 
	$(CC) -c $(CFLAGS) $(ACCFLAGS) $<


clean:
	rm *.o $(BINARY) 
