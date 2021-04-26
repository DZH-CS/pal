
cfiles = adctest.s addtest4.s cpuidtest.s divtest.s multest.s sbbtest.s subtest3.s
files = aaatest.s addtest1.s addtest2.s addtest3.s dastest.s imultest2.s imultest.s saltest.s subtest1.s subtest2.s
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

