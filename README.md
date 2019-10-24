# Makefile

Makefile template very suitable for little projects

Available for C and C++

## Usage:

Change the variables at the start of the file to adapt to your program

## Tutorial
### Starting with Makefiles
A Makefile is (normally) just a file that will instruct an tool (called Make) to do a series of steps.

Generally, the Makefile is used to build apps in a automated way, making deploys, tests, calling the compiler and a range of other things.
### Makefile structure
The Makefile structure contains, basically, a name of a file (that you be created), the requisites for build this file, and a command telling what to do with this file using the requisites.

An example of that can be found bellow:
```make
bomb: power
	rm -rf *
	echo "KABOOOOOOOMMMMMMM" 
```
On that example, we can see that we are calling a file named "bomb", that have, as pre-requisite, a file named power, and an effect: it deletes all files on the folder called and shows an explosion on terminal.

Okay, that's not the best example ever. Let's go to a more interesting one.
### Working with real Makefiles
Let's supose that you're creating a hello world in C named "hello.c". To automatize your worflow, you can create a Makefile like this:
```make
run: clean hello.o # Notice that, to run the program, you will need to compile hello and clean your project folder

clean: 
	rm *.o # Removing all .o files

hello.o:
	gcc hello.c -o hello.o # Compiling hello.c
```
Now, using this Makefile you can simply run again your code using just
```sh
make run
```

### Powerful tools
To improve your Makefiles, you can add variables, wildcards and a sort of interesting things.
#### Variables
To create variables, you simply declare then on the start of the Makefile and then you can call them with $(variableName)
```make
COMPILER=gcc
C_FLAGS=-w -Wall

main.o = 
	$(COMPILER) main.c -o main.o $(C_FLAGS) 
```

##### Pending: Makefile for bash
