
basec = badprog.c floattest.c goodprog.c inttest.c mainprog.c mathtest.c multtest.c stringtest.c
asmfun = areafunc.s  asmfunc.s  cpuidfunc.s  fpmathfunc.s  greater.s  square.s  testfunc.s
BOBJS:=$(basec:%.c=%.o)
OBJS:=$(asmfun:%.s=%.o)
PROG:=$(basec:%.c=%)
ELFS:=$(PROG) badprog.ld
all: $(BOBJS) $(OBJS) $(ELFS)
$(BOBJS): %.o: %.c
	gcc -c $< -o $@
$(OBJS): %.o: %.s
	as $< -o $@
badprog.ld: badprog.o testfunc.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 $^ -o $@
badprog: badprog.o testfunc.o
	gcc $^ -o $@
goodprog: goodprog.o testfunc.o
	gcc $^ -o $@
floattest: floattest.o areafunc.o
	gcc $^ -o $@
inttest: inttest.o square.o
	gcc $^ -o $@
mainprog: mainprog.o asmfunc.o
	gcc $^ -o $@
mathtest: mathtest.o fpmathfunc.o
	gcc $^ -o $@
stringtest: stringtest.o cpuidfunc.o
	gcc $^ -o $@
multtest: multtest.o greater.o
	gcc $^ -o $@
clean:
	@rm -rf $(BOBJS) $(OBJS) $(ELFS)

