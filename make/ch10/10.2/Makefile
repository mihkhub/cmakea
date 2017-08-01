# Compiling C programs
# n.o is made automatically from n.c with a recipe of the form
# $(CC) $(CPPFLAGS) $(CFLAGS) -c
#
# Compiling C++ programs
# n.o is made automatically from n.cc, n.cpp or n.C with a recipe of the form
# $(CXX) $(CPPFLAGS) $(CXXFLAGS) -c. We encourage you to the suffix '.cc' for C+ source files instead of '.c'.

objects = main.o command.o buffer.o utils.o api.o

edit : $(objects)
	$(CC) $(CPPFLAGS) $(CFLAGS) -o edit  $(objects)
client : $(objects)
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) -o client $(objects)

command.o : command.h
buffer.o : buffer.h
utils.o : utils.h
api.o : api.h

.PHONY : clean
clean : 
	$(RM) edit $(objects)
