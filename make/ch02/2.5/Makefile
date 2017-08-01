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
main.o : main.c defs.h
kbd.o : kbd.c defs.h command.h 
command.o : command.c defs.h command.h
display.o : display.c defs.h buffer.h
insert.o : insert.c defs.h buffer.h
search.o : search.c defs.h buffer.h
files.o : files.c defs.h buffer.h command.h
utils.o : utils.c defs.h

.PHONY : clean
clean :
	$(RM) edit  $(objects)
