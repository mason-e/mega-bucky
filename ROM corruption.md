## Corruption Testing

This is an extension of the ROM breakdown, but more inexact. I tested some of the unknown regions by corrupting them to see what gets broken.

### 8740 to 9150

Appears to be level data for Green Planet. I went and broke it in smaller chunks as well.

8740 to 8800: Partly breaks Act 3  
8800 to 8900: Partly breaks Acts 3 and 4  
8900 to 8A00: Breaks GP Act 1 (mostly palettes), very small amount of Act 2, some of Act 3  
8A00 to 8B00: Breaks Act 1-4 layouts pretty bad, Act 6 palette 
8B00 to 8C00: Breaks Acts 1 and 6 layouts pretty bad  
8C00 to 8D00: Pretty large Act 1 and 2 breaks  
8D00 to 8E00: Pretty large Act 2 break  
8E00 to 8F00: Pretty large Act 3 break  
8F00 to 9000: Pretty large Act 3 break  
9000 to 9100: Pretty large Act 4 and 5 break  
9100 to 9250: Pretty large Act 6 break  

### 96A0 to A200

Looks like level data for Red Planet. At this point, I am going to assume that other level data is placed after its tile data until I find otherwise.

### EF90 to FFC0

This is also level data (Magma Tanker), but I checked it since it appears in between scripts as well. But all I really noticed was the corrupt level data, as before.

### 10160 to 10430

Corrupts the loading of the title and stage select screens (graphics go gray, sound stutters), but can still navigate on them and start the game.

### 10510 to 11490

Now we're getting somewhere. This causes massive corruption; I couldn't even load up the game from the start, but was able to load up save states. Enemy and power up sprites often turn into the player character sprite. The screen shakes and changes colors, with palettes that aren't even defined in the ROM. The actual level layouts aren't _too_ altered considering everything else, but that may be because they are already in RAM. The music also seems intact, but I don't know enough to rule out if that is from the save state RAM as well.

### 114A0 to 114D0

Controls the display of the bottom bar, though not the values, as a peek in RAM shows the score and lives still stored internally. The bottom bar instead displays briefly after pressing game start on the title screen.

### 115A0 to 11A00

I had a few crashes here, but couldn't figure out the common thread causing them. Also affected palettes since at the time I thought palettes started later.

### 122A0 to 13000

When loading from the start, all is fine up to stage select, but then when loading a stage, as soon as it loads, the game crashes. I thought it was kind of funny that the game coincidentally starts playing its boss explosion sound right before the crash. The Blue Planet is the only one that doesn't crash immediately, but it doesn't last long. I can load up some save states, but they are pretty crash prone as well. There's a moderate amount of sprite glitching.

### 13000 to 13600

First five levels were fine through limited testing. Starting from Salvage Chute through the end, sprites start disappearing from levels, and certain things no longer work right (such as the up/down arrow levitation in Magma Tanker). Crash prone, of course.

### 13600 to 13C00

Escape is still missing some sprites but other levels I checked were intact. Game seems to crash any time a cutscene should play.

### 13C20 to 13FC0

More crashes when cutscenes trigger.

### 14010 to 14510

Sprites for player characters and some enemies are very corrupted, in all levels. The game seems to mostly work (shooting, collecting power-ups, jumping, collisions), but I did experience some slow movement. Also crash prone.

### 14510 to 14A10

Some missing sprites, but didn't notice many - just in the opening cutscene, Green Planet and the Yellow Planet boss.

### 14A10 to 15010

Some more sprite corruptions, mainly seems to take the form of loading the wrong sprite. For example, explosions use garbled sprites of the player character.

### 15010 to 15810

Similar to above, sprite mix ups. Most are in the opening cutscene, but some enemies affected.

### 15810 to 16010

Again more sprite mix ups. The power up sprites were wrong here. Escape has many corrupt sprites (player character invisible in the plane), some in Magma Tanker as well.

### 16010 to 16810

The sprite corruption is still present, but finally, some real bugs! The player character dies almost instantly in every level, so I'm not able to get much further beyond that. In part of Cell, where I didn't die instantly, I was able to move through the blocks. The most interesting effect I could produce from this bug was loading up my game complete save. Bucky gets stuck on the first credits cutscene dying until game over while the credits theme plays. After the game over, I got the stage select screen with all the completed planets grayed out, and when I selected one the game crashed. This isn't very insightful for hacking, but it was fun to see.

### 16810 to 16C10

More bugs. My player character appears embedded in the ground and can't walk, only jump out. When I jump out I can't see them move, but they appear in another location as expected. I can clip upwards through the bottom of other blocks.

### 17600 to 17B00

Crashes on all cutscenes immediately.

### 17B00 to 18000

Crashes on ending where credits would start. Opening cutscene and the pre-cell cutscene crash shortly after starting.

### 18000 to 18800

Game crashes everywhere. Can't boot up or load any save states without instant crash.

### 18800 to 19000

Same as above, although the copyright screen loaded, but then it crashed everywhere else.

### 19000 to 19800

Corrupted sounds and music, with a few crash tendencies. I did catch bits of the Red Planet melody playing during the pre-Cell cutscene, but in the wrong channel.

### 19800 to 1A000

More corrupted music, but instead of weird noise like the previous set, it mostly just seems to be missing channels. Green Planet has no music at all, others are missing a few channels. It seems like basslines are most commonly intact. Some of the melody lines pop in and out but aren't consistent. Sound effects are intact.