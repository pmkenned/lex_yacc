LEX = flex
YACC = bison
LFLAGS ?=
YFLAGS ?= -d

TARGET = ansi_c

.PHONY: all clean

all: $(TARGET)

ARGS ?= foo.c
run: $(TARGET)
	./$(TARGET) $(ARGS)

clean:
	rm -f $(TARGET) lex.yy.c ansi_c.tab.c ansi_c.tab.h

$(TARGET): lex.yy.c ansi_c.tab.c
	$(CC) $(CFLAGS) -o $@ $^

lex.yy.c: ansi_c.l
	$(LEX) $(LFLAGS) $<

ansi_c.tab.c: ansi_c.y
	$(YACC) $(YFLAGS) $<
