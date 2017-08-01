#It is standarde proctice for every makefile to have a variable named objects, OBJECTS, objs,
# OBJS, obj, or OBJ whi is a list of all boject file names.
objects =  main.o kbd.o command.o display.o \
	insert.o search.o files.o utils.o
# Whe split each long line into two lines using backslash/newline; this is like using one long line

edit : $(objects)
	$(CC) -o edit $(objects)	
# It is not necessary to spell out the recipes for compiling the individual C source files,
# because make can figure them out; it has an implicit rule for updating a '.l' file from
# a correspondingly named '.c' file using a '$(CC) -c' command.
# Because implicit rules are so convenient, they are important, You will see them used frequently.
$(objects) : defs.h
kbd.o command.o files.o : command.h
display.o insert.o search.o files.o : buffer.h
.PHONY : clean
clean :
	$(RM) edit  $(objects)
