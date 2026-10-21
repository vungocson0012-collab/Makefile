###############
## PATTERNS ##
###############

DEBUG_MODE = 1

DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17 # make build CXX_STANDARD=c++14
CXX_WARNINGS = -Wall -Wextra -Wpedantic

CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
# LDFLAGS = -lmath

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) 

CXX_OBJECTS = my_lib.o main.o

build: my_lib.o main.o	
	echo $(CXX_COMPILER_CALL)
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(EXECUTABLE_NAME)

main.o:	
	$(CXX_COMPILER_CALL) main.cc -c

my_lib.o:
	$(CXX_COMPILER_CALL) my_lib.cc -c

execute:
	./main

clean:
	rm -f *.o
	rm -f main

###############
## PATTERNS ##
###############

# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequisites

%.o: %.cc # với mỗi file .cc tạo ra file .o tương ứng cùng tên
	$(CXX_COMPILER_CALL) -c $< -o $@

