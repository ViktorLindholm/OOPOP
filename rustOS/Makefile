# .m32 = för att kompilera i 32 bit mode
# --32 = 32 bit

ASSEMBLY 		= --32
LINKERSCRIPT 	= -melf_i386
OBJECTS 		= loader.o kernel.o
RUST 			= .m32

%.o: %.rs
	rustc $(RUST) -o $@ -c $<

%.o: %.s
	as $(ASSEMBLY) -o $@ $<

kernel.bin: linker.ld $(OBJECTS)
	ld $(LINKERSCRIPT) -T $< -o $@ $(OBJECTS)

install: kernel.bin
	sudo cp $< /boot/kernel.bin


# fortsätt på 17 min 