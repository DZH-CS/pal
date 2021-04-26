
cfiles = convert.s
files = cmpstest1.s cmpstest2.s movstest1.s movstest2.s movstest3.s reptest1.s reptest2.s reptest3.s reptest4.s scastest1.s scastest2.s stostest1.s strcomp.s strsize.s
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
clean:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS)

