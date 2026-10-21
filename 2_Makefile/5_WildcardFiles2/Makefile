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

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) 

CXX_SOURCES = $(wildcard *.cc)

#patsubt: $(text:pattern=replacement) : thay thế chuỗi theo mẫu
CXX_OBJECTS = $(patsubst %.cc, %.o, $(CXX_SOURCES))

build: $(CXX_OBJECTS)	
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(EXECUTABLE_NAME)

execute:
	./$(EXECUTABLE_NAME)

clean:
	rm -f *.o
	rm -f $(EXECUTABLE_NAME)

###############
## PATTERNS ##
###############

# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequisites

%.o: %.cc # với mỗi file .cc tạo ra file .o tương ứng cùng tên
	$(CXX_COMPILER_CALL) -c $< -o $@

