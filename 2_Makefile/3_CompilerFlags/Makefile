###############
## VARIABLES ##
###############

# make -p: help

# Note: Variables can only be strings
# Note: Single or double quotes for variable names or valus have no meaning to make

DEBUG_MODE = 1

# CC: Program fo r ompiling C programs; default cc
# CXX: Program for compiling C++ programs; default g++
# CFLAGS: Extra flags to give to the C compiler
# CXXFLAGS: Extra flags to give to the C++ compiler
# CPPFLAGS: Extra flags to give to the C preprocessor (tiền sử lý)
# LDFLAGS: Extra flags to give to the linker

DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17 # make build CXX_STANDARD=c++14
CXX_WARNINGS = -Wall -Wextra -Wpedantic

CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
LDFLAGS = -lmath

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

COMPILER_CALL = $(CXX) $(CXXFLAGS) # cú pháp lấy giá trị biến $()

build: my_lib.o main.o	# kiểm tra target my_lib.o và main.o đc tạo chưa
# đc tạo rồi thì chạy target build
	echo $(COMPILER_CALL)
	$(COMPILER_CALL) main.o my_lib.o $(LDFLAGS) -o $(EXECUTABLE_NAME)

main.o:	#target có thể đặt giống tên file, đặt cho có ý nghĩa
	$(COMPILER_CALL) main.cc -c

#Form đặt: 
#	file_đầu_ra: các_file_đầu_vào
#		lệnh tạo file_đầu_ra

my_lib.o:
	$(COMPILER_CALL) my_lib.cc -c

execute:
	./main

clean:
	rm -f *.o
	rm -f main