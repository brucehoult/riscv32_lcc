#
# Makefile for Libs

LCCDIR =../..
CC = ${LCCDIR}/lcc
AS = ${LCCDIR}/../../binutils/bin/as

CFLAGS = -Wo-lccdir=${LCCDIR} -S -D__TCS_V2__ -w -v


CSRCS = $(wildcard *.c)
ASRCS = $(patsubst %.c,%.s,$(CSRCS))
BIN = ${CURDIR}.o

.PHONY:		all clean

all:		$(BIN)

%.s:%.c
	$(CC) $(CFLAGS) $<

$(BIN):$(ASRCS)
	$(AS) -o $@ $^

clean:
		rm -f *~ $(OBJS) $(BIN)
