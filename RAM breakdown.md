# RAM Breakdown

This file is basically the same concept as my ROM breakdown, but with values in RAM. RAM values of course are read and written to for things like the score, character health, etc. I hope that by finding values in RAM I can get a better sense of how they are written from ROM and use that to manipulate the ROM.

## Known Values

### Current Score

Written to 0046 and 0047. The values are not stored as a two-byte number but rather two single bites. For example, a score of 5000 (dec) is not stored as its hex value $1388 across both addresses but rather as $32 and $00 (50 and 00 dec).

### High Score

Stored at 0048 and 0049, also split in the same way as current score.

### Lives

004C

### Health

Current: 05A0  
Max: 0690

### Power

Current Charge: 0041  
Bucky Max: 0690  