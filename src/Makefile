PROG = blinky

CC = arm-none-eabi-gcc
LD = arm-none-eabi-gcc
CP = arm-none-eabi-objcopy
CFLAGS = -c -mcpu=cortex-m4 -mthumb -Wall -O0
LFLAGS = -nostdlib -T stm32f401-rom.ld

OBJS = startup.o \
       main.o
RMPROG = $(PROG).elf \
         $(PROG).bin \
		 $(PROG).map

all: $(PROG).elf

$(PROG).elf: main.o startup.o
	$(LD) $(LFLAGS) $^ -o $@
	$(CP) $(PROG).elf -O binary $(PROG).bin

%.o: %.c
	$(CC) -c $(CFLAGS) $< -o $@

clean: 
	rm -f $(OBJS) $(RMPROG)