CC =		cc
CFLAGS =	-c -fPIC -std=c99 -Wall -Werror -O0 -g -I/usr/local/include
LDFLAGS =	-shared -L/usr/local/lib -lopenal -lvorbisfile -ljson-c
RM =		rm -f
TARGET_LIB =	libfmodstudio.so
HDRS =		fmoad-cailin.h al.h

ifeq ($(shell uname),Linux)
	CFLAGS += -D_DEFAULT_SOURCE=1 -Wno-unused-variable
	LDFLAGS += -lbsd
endif

.PHONY: all
all: libfmodstudio.so

%.o: %.c $(HDRS)

libfmodstudio.so: fmoad-cailin.o al.o
	$(CC) $(LDFLAGS) -o $@ $^

.PHONY: clean
clean:
	$(RM) libfmodstudio.so fmoad-cailin.o al.o
