# ROM Breakdown

This file is for tracking "regions" of the PRG ROM as I determine them. This info can be useful, for example, when searching a specific byte value later on (say I wanted to find the byte for a score) and using the known ranges to eliminate some possibilities (a score value is probably not in level data). My ranges are not exact, as I didn't see a sense in finding the exact address where something starts and ends. Because it's not exact to every byte, it's also possible that other data might be mixed up (for all I know a score value _could_ be in with level data), but it's reasonable to assume based on the findings so far that similar things are generally grouped together.

## Undetermined Ranges
0000 to 3100 (first part of ROM)  
32A0 to 8090 (appears between tiles, but larger range than others)  
8740 to 9250 (between tiles)  
96A0 to A2B0 (between tiles)  
A6C0 to AED0 (between tiles)  
AF50 to C0B0 (between tiles)  
C9D0 to D2F0 (between tiles)  
DA40 to EB50 (between tiles)  
EF90 to 10110 (between tiles and scripts)  
10160 to 10430 (between scripts)  
10510 to 114A0 (between scripts)  
114A0 to 114E0 (between scripts)  
11590 to 11AXX (between scripts and palettes)  
11BXX to 11C40 (between palettes and scripts)  
11D70 to 12200 (between scripts)  
122A0 to 13C10 (between scripts)  
13C10 to 16C60 (between scripts, but larger range than others)  
17580 to 20000 (end of ROM)

## Determined Ranges

### 3100 to 32A0
Escape tiles

### 8090 to 8740
Green Planet tiles

### 9250 to 96A0
Red Planet tiles

### A2B0 to A6C0
Blue Planet tiles

### AED0 to AF50
Salvage Chute tiles

### C0B0 to C9D0
Yellow Planet tiles

### D2F0 to DA40
Cell tiles

### EB50 to EF90
Magma Tanker tiles

### 10110 to 10160
Title screen script

### 10430 to 10510
Copyright screen script

### 114A0
GAME START script (not sure where in game this appears)

### 114E0 to 11500
Status bar script (and logic?)

### 11510 to 11590
Stage name script

### 11AXX to 11BXX
Palettes. I marked this more inexactly since I only checked a few palettes from around the beginning and end of the game.

### 11C40 to 11D70 
End credits script

### 12200 to 122A0 

Cell script

### 13C10
PASS WORD script (I think this is when you are _given_ a password)

### 16C60 to 17580
Cutscene scripts (prologue, between levels and epilogue)