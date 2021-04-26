
basec = calctest.c condtest.c csetest.c sums.c tempconv.c vartest.c
BOBJS:=$(basec:%.c=%.o)
PROG:=$(basec:%.c=%)
ELFS:=$(PROG)
all: $(BOBJS) $(OBJS) $(ELFS)
$(BOBJS): %.o: %.c
	gcc -c $< -o $@
$(ELFS): %: %.o
	gcc $^ -o $@
clean:
	@rm -rf *$(BOBJS) $(OBJS) $(ELFS)

