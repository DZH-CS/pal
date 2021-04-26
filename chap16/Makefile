
mulasm = readtest3.s fileconvert.s
asmelf = cpuidfile.s readtest1.s readtest2.s
asmfun = sizefunc.s convert.s

BOBJS:=$(asmelf:%.s=%.o)
OBJS:=$(asmfun:%.s=%.o)
PROG:=$(asmelf:%.s=%)

all: $(BOBJS) $(OBJS) $(PROG) fileconvert
$(BOBJS): %.o: %.s
	as $< -o $@
$(OBJS): %.o: %.s
	as $< -o $@
$(PROG): %: %.o
	ld $< -o $@
fileconvert: fileconvert.o sizefunc.o convert.o
	ld $^ -o $@
#readtest3: readtest3.o # 有问题暂时不进行处理
clean:
	@rm -rf $(BOBJS) $(OBJS) $(ELFS)

