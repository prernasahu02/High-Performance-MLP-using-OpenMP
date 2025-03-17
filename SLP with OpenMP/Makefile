# Defines
CC         = gcc
OBJ_DIR    = ./obj
SRC_DIR    = ./src
INCL_DIR   = ./include
OBJECTS    = $(addprefix $(OBJ_DIR)/, read_csv.o write_csv.o forward_propagation.o back_propagation.o mlp_trainer.o mlp_classifier.o)
INCLUDES   = $(addprefix $(INCL_DIR)/, read_csv.h write_csv.h forward_propagation.h back_propagation.h mlp_trainer.h mlp_classifier.h parameters.h)
EXECUTABLE = MLP
# CFLAGS   = -g -Wall (for Normal Execution)
# CFLAGS   = -Wall -O2 -fopenmp -pg (for Functional Profiling)
# CFLAGS   = -Wall -O0 -fprofile-arcs -ftest-coverage # For Line profiling 

# CFLAGS -> SRC for Hardware Profiling

CFLAGS     = -O2 -Wall -fopenmp -I./include
LDFLAGS    = -llikwid -lm
TARGET     = perceptron
SRC        = src/main.c src/back_propagation.c src/forward_propagation.c src/mlp_classifier.c src/mlp_trainer.c src/read_csv.c src/write_csv.c

# Generate the target file to get the Hardware Profiling
$(TARGET): $(SRC)
$(CC) $(CFLAGS) $(SRC) -o $(TARGET) $(LDFLAGS)

# Generate the executable file
$(EXECUTABLE): $(SRC_DIR)/main.c $(OBJECTS)
	$(CC) $(CFLAGS) $< $(OBJECTS) -o $(EXECUTABLE) -I $(INCL_DIR) -lm

# Compile and Assemble C source files into object files
$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c $(INCLUDES)
	$(CC) $(CFLAGS) -I $(INCL_DIR) -c $< -o $@

# Clean the generated executable file and object files
clean:
# 	rm -f $(TARGET)  (To clean the generated target file)
	rm -f $(OBJECTS)
	rm -rf $(EXECUTABLE)*
