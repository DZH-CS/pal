
files = bcdtest.s floattest.s inttest.s mmxtest.s convtest.s movsxtest.s quadtest.s ssefloat.s fpuvals.s movsxtest2.s movzxtest.s sse2float.s ssetest.s
OBJS:=$(files:%.s=%.o)
ELFS:=$(files:%.s=%)
all: $(OBJS) $(ELFS)
$(OBJS): %.o: %.s
	as $< -o $@
$(ELFS): % : %.o
	ld $< -o $@
clear:
	@rm -rf $(OBJS) $(ELFS)

