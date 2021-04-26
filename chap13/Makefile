
# 错误的代码无法编译通过
bad = badregtest.c
baseac = alttest.c areatest.c asmtest.c cfunctest.c changedtest.c globaltest.c jmptest2.c jmptest.c mactest1.c mactest2.c memtest.c movstest.c regtest1.c regtest2.c regtest3.c sincostest.c
BOBJS:=$(baseac:%.c=%.o)
BELFS:=$(baseac:%.c=%)
all: $(BOBJS) $(BELFS)
$(BOBJS): %.o: %.c
	gcc -c $< -o $@
$(BELFS): % : %.o
	gcc $< -o $@
clean:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS) $(BOBJS) $(BELFS)

