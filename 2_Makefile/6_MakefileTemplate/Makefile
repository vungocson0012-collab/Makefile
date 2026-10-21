DEBUG_MODE = 1
SOURCE_DIR = src
INCLUDE_DIR = include
BUILD_DIR = build

DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17 # make build CXX_STANDARD=c++14
CXX_WARNINGS = -Wall -Wextra -Wpedantic

CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
CPPFLAGS = -I $(INCLUDE_DIR)

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) $(CPPFLAGS)

CXX_SOURCES = $(wildcard $(SOURCE_DIR)/*.cc)

#patsubt: $(text:pattern=replacement) : thay thế chuỗi theo mẫu
CXX_OBJECTS = $(patsubst $(SOURCE_DIR)/%.cc, $(BUILD_DIR)/%.o, $(CXX_SOURCES))
create:
	mkdir -p $(BUILD_DIR)

build: create $(CXX_OBJECTS)	
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(BUILD_DIR)/$(EXECUTABLE_NAME)

execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)

clean:
	rm -f $(BUILD_DIR)/*.o
	rm -f $(BUILD_DIR)/$(EXECUTABLE_NAME)

###############
## PATTERNS ##
###############

# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequisites

$(BUILD_DIR)/%.o: $(SOURCE_DIR)/%.cc | create
	$(CXX_COMPILER_CALL) -c $< -o $@