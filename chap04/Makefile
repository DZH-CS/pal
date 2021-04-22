objects = cpuid.o cpuid2.o

cpuid = cpuid
cpuid2 = cpuid2
cpuid2-main = cpuid2-main

all: $(objects) $(cpuid)  $(cpuid2) $(cpuid2-main)

$(objects): %.o: %.s
	as $< -o $@

$(cpuid): cpuid.o
	ld -o cpuid cpuid.o

$(cpuid2): cpuid2.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 -o cpuid2 cpuid2.o

$(cpuid2-main): cpuid2-main.s
	gcc $< -o $@

clean:
	rm -rf $(objects) $(cpuid)  $(cpuid2) $(cpuid2-main)

