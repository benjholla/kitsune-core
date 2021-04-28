KITSUNE_PATH = ../../../../../bin
KTCC = $(KITSUNE_PATH)/bin/ktcc
KTLIB = $(KITSUNE_PATH)/lib/libkitsune.a

KT_CFLAGS = -fpic -I$(KITSUNE_PATH)/include
KT_LDFLAGS = -L$(KITSUNE_PATH)/lib -lkitsune -ldl

SOURCE = ex1.c
CFLAGS = -O2 -fomit-frame-pointer $(KT_CFLAGS)
 
all: ex1 ex1.so
 
%.o: %.c
	$(KTCC) $(CFLAGS) -c $^
 
ex1: ex1.o
	$(CC) -o $@ $^ $(KT_LDFLAGS)

ex1.so: ex1.o
	$(CC) -o $@ -shared $^ $(KT_LDFLAGS)

clean:
	rm *.o || true
	rm ex1 || true
	rm ex1.so || true
