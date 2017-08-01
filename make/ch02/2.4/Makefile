#It is standarde proctice for every makefile to have a variable named objects, OBJECTS, objs,
# OBJS, obj, or OBJ whi is a list of all boject file names.
objects =  main.o kbd.o command.o display.o \
	insert.o search.o files.o utils.o
# Whe split each long line into two lines using backslash/newline; this is like using one long line

edit : $(objects)
	$(CC) -o edit $(objects)	

main.o : main.c defs.h
	$(CC) -c main.c
kbd.o : kbd.c defs.h command.h 
	$(CC) -c kbd.c
command.o : command.c defs.h command.h
	$(CC) -c command.c
display.o : display.c defs.h buffer.h
	$(CC) -c display.c
insert.o : insert.c defs.h buffer.h
	$(CC) -c insert.c
search.o : search.c defs.h buffer.h
	$(CC) -c search.c
files.o : files.c defs.h buffer.h command.h
	$(CC) -c files.c
utils.o : utils.c defs.h
	$(CC) -c utils.c
clean :
	$(RM) edit  $(objects)
