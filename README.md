# avr8-vga-assembly
An VGA monochrome driver using a single atmega328. This is my final year college project at 2014

This program is written in handwritten assembly (ie, not machine generated). This thing can display 64x32 character on a standard VGA monitor (640x480).

### How it's work

1. An ascii code representing onscreen character is stored in the RAM. ATMEGA328 has 2048 byte RAM, so it's corespondence with 64x32 character that can be displayed

2. A font table is stored in the ROM. The layout is designed so that the lower byte address of the font table corespond with the actual ascii code.

3. Bitmap data is written in a 8 bit block to output pin which then converted to serial data using 74HC165

### Performance and timing

There are a few trick used to achieve the required performance:

1. Look up table instead of conditional statement.
2. Loop unrolling

This thing probably didn't have practical use now, but a good learning material nevertheless

