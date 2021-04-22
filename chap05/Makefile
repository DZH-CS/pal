
cfiles = movtest3.s cmovtest.s
files = bubble.s cmpxchg8btest.s cmpxchgtest.s movtest1.s movtest2.s movtest4.s sizetest1.s sizetest2.s sizetest3.s swaptest.s xaddtest.s pushpop.s
OBJS:=$(files:%.s=%.o)
COBJS:=$(cfiles:%.s=%.o)
ELFS:=$(files:%.s=%)
CELFS:=$(cfiles:%.s=%)
all: $(OBJS) $(ELFS) $(COBJS) $(CELFS)
$(OBJS): %.o: %.s
	as $< -o $@
$(ELFS): % : %.o
	ld $< -o $@
$(COBJS): %.o: %.s
	as $< -o $@
$(CELFS): % : %.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 $< -o $@
clear:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS)

