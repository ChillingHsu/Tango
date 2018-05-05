CC = gcc
CFLAGS = -W -Wall -Wextra

OBJS = autodriver.o

all: autodriver

autodriver: $(OBJS)
	$(CC) $(LDFLAGS) -o autodriver $(OBJS)
	chown root autodriver
	chmod +s autodriver

autodriver.o: autodriver.c

clean:
	rm -f *.o autodriver

.PHONY: clean
