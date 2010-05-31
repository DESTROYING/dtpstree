CXXFLAGS ?= -g -O2
CXXFLAGS += -pedantic -Wall -Wno-long-long
LDLIBS := -lkvm

.PHONY: all man clean

all: dtpstree

man: man1/dtpstree.1

man1/%.1: % man1/%.1.in
	help2man -I $@.in -Nn '$(shell sed -e '$$ s|^// ||p;d' $<.cpp)' -o $@ $(shell realpath $<)

clean:
	rm -f dtpstree $(wildcard *core)
