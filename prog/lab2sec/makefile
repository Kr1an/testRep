APP := app
SRCS := main.c
all: $(SRCS)
	gcc -Wall -ansi --pedantic -g -o $(APP) $^ -lm
lint:
	splint -f splintrc $(SRCS)

indent:
	indent --linux-style $(SRCS)

valgrind:
	valgrind --leak-check=yes ./$(APP)

pass: all indent lint valgrind

clean:
	rm -f *.o

cleanall: clean
	rm -f $(APP)
