# Name: David Hunt
# Course: CS178 Build Automation for DevOps and QA
# CRN: 76718
# Date: 09/10/2018
# Assignment: Makefile for ServerCountThrees
# This Makefile compiles and runs the ServerCountThrees program

# Defining variables for file names and directories
PROGRAM_NAME = ServerCountThrees
READ_NAME = readInt32BitLE
DATA_NAME = threesData.bin
DATA_DIR = /home/david/ServerCountThrees/data
TARGET_DIR = /home/david/ServerCountThrees/build

# test target that creates build directory with data and exec files and runs exec
test : $(PROGRAM_NAME)
	mkdir $(TARGET_DIR); \
	cp $(DATA_DIR)/$(DATA_NAME) $(TARGET_DIR)/.; \
	cp $(PROGRAM_NAME) $(TARGET_DIR)/.; \
	$(TARGET_DIR)/$(PROGRAM_NAME)

# Creates target executable file from object files
$(PROGRAM_NAME) : $(PROGRAM_NAME).o $(READ_NAME).o
	gcc -g -o $(PROGRAM_NAME) $(PROGRAM_NAME).o $(READ_NAME).o

# Compiles program source file into program object file
$(PROGRAM_NAME).o : $(PROGRAM_NAME).c
	gcc -g -c $(PROGRAM_NAME).c -o $(PROGRAM_NAME).o

# Compiles read source files into rea object file	
$(READ_NAME).o : $(READ_NAME).c $(READ_NAME).h
	gcc -g -c $(READ_NAME).c -o $(READ_NAME).o

# cleans up object files and target directory
clean :
	rm *.o $(PROGRAM_NAME) -dr $(TARGET_DIR)
