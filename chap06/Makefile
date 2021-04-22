
basec = ifthen.c for.c
cfiles = signtest.s betterloop.s loop.s calltest.s
files = cmptest.s jumptest.s paritytest.s
BOBJS:=$(basec:%.c=%.o)
OBJS:=$(files:%.s=%.o)
COBJS:=$(cfiles:%.s=%.o)
ELFS:=$(files:%.s=%)
CELFS:=$(cfiles:%.s=%)
BELFS:=$(basec:%.c=%)
all: $(OBJS) $(ELFS) $(COBJS) $(CELFS) $(BOBJS) $(BELFS)
$(OBJS): %.o: %.s
	as $< -o $@
$(ELFS): % : %.o
	ld $< -o $@
$(COBJS): %.o: %.s
	as $< -o $@
$(CELFS): % : %.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 $< -o $@
$(BOBJS): %.o: %.c
	gcc -c $< -o $@
$(BELFS): % : %.o
	gcc $< -o $@
clear:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS) $(BOBJS) $(BELFS)

