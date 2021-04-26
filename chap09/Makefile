
cfiles = fpmath1.s
files = fcmovtest.s fcomitest.s fcomtest.s fpmath2.s fpuenv.s fpusave.s fscaletest.s getstatus.s logtest.s premtest.s roundtest.s setprec.s stacktest.s trigtest1.s trigtest2.s
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

