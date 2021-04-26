
basec = ctest.c
cfiles = paramtest1.s paramtest2.s paramtest3.s
files = area.s functest1.s functest2.s functest3.s functest4.s
BOBJS:=$(basec:%.c=%.o)
OBJS:=$(files:%.s=%.o)
COBJS:=$(cfiles:%.s=%.o)
ELFS:=functest1 functest2 functest3
MELFS:=functest4
CELFS:=$(cfiles:%.s=%)
BELFS:=$(basec:%.c=%)
all: $(OBJS) $(ELFS) $(COBJS) $(CELFS) $(BOBJS) $(BELFS) $(MELFS)
$(OBJS): %.o: %.s
	as $< -o $@
$(ELFS): % : %.o
	ld $< -o $@
$(MELFS): % : functest4.o area.o
	ld functest4.o area.o -o $@
$(COBJS): %.o: %.s
	as $< -o $@
$(CELFS): % : %.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 $< -o $@
$(BOBJS): %.o: %.c
	gcc -c $< -o $@
$(BELFS): % : %.o
	gcc $< -o $@
clean:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS) $(BOBJS) $(BELFS) $(MELFS)

