LEX = flex
YACC = bison
LFLAGS ?=
YFLAGS ?= -d

TARGET = calc

.PHONY: all run clean

all: $(TARGET)

run: $(TARGET)
	./$(TARGET)

clean:
	rm -f $(TARGET) lex.yy.c calc.tab.c calc.tab.h

$(TARGET): lex.yy.c calc.tab.c
	$(CC) $(CFLAGS) -o $@ $^

lex.yy.c: calc.l
	$(LEX) $(LFLAGS) $<

calc.tab.c: calc.y
	$(YACC) $(YFLAGS) $<
