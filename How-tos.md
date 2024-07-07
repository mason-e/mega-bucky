# How to Hack Bucky O'Hare

This document is for techniques I learned in my Bucky O'Hare ROMhack, mostly for my own reference back. I'm sure many of these work for other NES games as well, but not completely.

Abbreviations:

TLP = Tile Layer Pro

## Editing Font

Text tiles were easy to find in TLP in my case, for both the source and destination game. The only thing I learned to watch out for is that sometimes text can appear in multiple places (for reasons I don't entirely understand), so it's best to scan the whole thing before starting to replace text. The tiles are easy to replace since each character is a single tile.

## Identifying Game Script

1. Open the Tile Viewer in Mesen when the game is running.
2. Note where alphabet and number characters' "Tile Index" begins - in this case from address $01.
3. Create a table file with them starting A at $01 thru Z, then 0 starts at $1B
4. Open the Mesen Memory Viewer, select the PRG ROM, load the table file in, and when scrolling through the script should eventually be visible on the right side.

### Editing Game Script

I can edit the game's script by replacing the address in memory with the tile index address of the desired letter, but I'm not sure how to go beyond the scope of the space I already have. I would likely have to shift the entire ROM which undoubetdly would have a lot of consequences. Or stick the new script at the ROM's unused memory and find a way to use those addresses instead.

## Sprite/Tile Editing

This will probably be a large section since there are a lot of elements that go into it. I'm going to use the word "sprite" and "tile" pretty interchangeably here, basically to mean any graphical element, whether it's actually a sprite (object) or scenery element.

### Finding Sprites in CHR ROM

With TLP, technically I could scroll through the loaded ROM and visually identify tiles, but it's really hard to identify anything other than text, since very few complete sprites are made up of just one 8x8 pixel tile.

Mesen's Tilemap Viewer and Sprite Viewer both work similarly. An issue I had in Bucky is that sometimes they don't show the data I want, but eventually realized if I keep re-pausing the emulator it'll show at some point. Once the sprites are there, I can hover over them and get the Tile Address (CHR) value. Then I can plug these values into TLP (making sure to go relative since the CHR memory doesn't start at $00000), which will take me to the tile.

### Finding Sprites Currently in Memory

In the Sprite Viewer and Tilemap Viewer, the tiles in use currently are loaded into memory addresses $00 through $FF (Pattern Tables). So if for example a blank sky tile is at $BD and a cloud uses BE BF C0 C1, I could find BE BF C0 C1 and replace them with BD BD BD BD if I want it to just be sky there.

As far as I can tell, all the tiles for the background/scenery are grouped in 32x32 pixel (4x4 tile) sizes in BOH. Once I realized this, I can easily find a given piece of scenery since Mesen conveniently lets me show the 32x32 gridlines in the Tilemap Viewer.

### Changing the Colors of Sprites

Once again Sprite Viewer and Tilemap Viewer are our friends, as well as the Palette Viewer. With any of these tools, for a given sprite I can find the palette it uses. The palette uses hex indexes that correspond to a color, so a palette might look something like 0F 01 20 10. If I can find 0F 01 20 10 in a hex editor that will likely be that palette, and I can replace any of them with a different color (sometimes only 01 20 10 in this example might show results).

Colors can also be changed by editing _within_ the palette in TLP, i.e. change some pixels that use the third color to use the second color.

#### TODO

Need to learn how to set a tile to an entirely different palette, not just change the colors within. 

## Function Editing

Mesen has a Profiler tool, which shows functions being called. There is a lot of noise in here (probably from constant graphical redraws), but near the bottom I could see counts going up when I'd fire my gun, jump, etc. TBD on getting anything actually useful out of this.