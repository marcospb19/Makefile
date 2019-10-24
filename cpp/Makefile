# Final program name
PROGRAM =

# Default target and pseudo-targets
.DEFAULT_GOAL = $(PROGRAM)
.PHONY = clean
.PHONY = install

# Compiler, Compilation flags, link flags
CC = clang++ # g++
CFLAGS = -O2 -Wall -Wextra -Wshadow -std=c++11
LDFLAGS =

# Object files to be built
OBJECTS = mytimer.o time.o



### Main targets
$(PROGRAM): $(OBJECTS)
	$(CC) $(LDFLAGS) -o $(PROGRAM) $(OBJECTS)

%.o: %.cpp
	$(CC) $(CFLAGS) -c $^ -o $@
###



### Pseudo-targets
clean:
	@rm $(OBJECTS) 2> /dev/null || exit 0

install: $(PROGRAM)
	@sudo cp $(PROGRAM) /usr/bin/    && \
		echo "Installed, Thank you!" ||  \
		echo "Some error occured."
###
