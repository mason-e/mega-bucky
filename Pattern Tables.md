# Pattern Tables

This is a list of CHR ROM (relative) addresses for the pattern tables of each act*. I did this so I can find tiles that repeat in different levels, which will require me to be careful about how I replace them.

Each pattern table has a total of 256 tiles, 16x16. Most of them are broken into two sets of 8x16, but I noticed a few places where it is 16x16 - that, or the sets happened to be adjacent. I've written them down as if they are all two sets.

The conclusion I eventually reached is that graphics don't really overlap. There are tile _sets_ used between multiple levels, but not really any individual tiles reused, except for things that are obviously the same, such as the robo snakes. Sets that could overlap with another level are indicated with an asterisk (*).

*Not actually each act, but each save state I made, which was on every screen change, but the game has some multi-act screens.

### Special Addresses
There are a couple instances where I noticed that the tilesets shift as scenery animates. These are listed here since they have multiple addresses.

"Lava/Water Set" (LWS) = 1000, 1800 and 2000:  
Used in all of the planet stages, but the individual tiles are unique per planet, so as long as any edits are kept within the same sub-group, there shouldn't be overlap. I also couldn't actually find any tiles used in the Yellow Planet. Also, the lava that uses some of these sets at the end of Escape doesn't appear to overlap.

"Mecha Set" (MS) = 12000, 12800, 13000, 13800:  
Used for the robo snakes that appear in Blue Planet and Magma Tanker, the water in the Salvage Chute dark areas, the "lava" and grubs in penultimate Salvage Chute, and conveyor belts in Cell/Magma Tanker.

"Parallax Block Set" (PBS) = 0000, 0800, 8000, 9F00, E000, E800, F000, 1A000, 1A800, maybe more; these appear to only use the blocks in the sets and nothing else

## Green Planet

Act 1, 2: 0000, 0800*  
Act 3, 4: 1F000, LWS  
Act 5: 1F000, 3000* (big toad ships)  
Act 6: 1F000, 7000* (boulder thrown) 

## Red Planet

Act 1-4: 6000, LWS   
Act 5, 6: 4000, 1800 (but second set may be unused)  
Act 7, 8: 9800* (ball only), PBS  
Act 9: 9800* (ball only), PBS?

## Blue Planet

Act 1-5: MS, 3800  
Act 6: 1F800 (nothing?), 3800  
Act 7, 8, 9: 4800, 3800  
Act 10: 4800, LWS  

## Yellow Planet

Act 1-5: 3000* (big toad ships), 5800  
Act 6: 6800, 7000* (planetoids)    
Act 7: 9000* (rollercoaster), 5800  
Act 8: 6800, LWS  

## Cell

Act 1: 5000, MS  
Act 2, 3: 5000, MS  
Act 4: 5000, PBS  
Act 5-6: 5000, MS  
Act 7: 5000, PBS  
Act 8: 5000, 7800  
Act 9: 5000, MS  

## Salvage Chute
Act 1-6: A000, A800  
Act 7-9: A000, MS  
Act 10: 9000* (top of boss), 9800* (after ball)  

## Magma Tanker
Act 1-4: 0800* (only uses 0F80 through 0FD0), B800  
Act 5, 6: B000, B800  
Act 7: MS, B800  
Act 8-10: 8000, 8800  
Act 11-13: MS, B800  
Act 14: 1E000, 1E800  

## Escape

Act 1: C000, C000  
Act 2: C000, C800  
Act 3: C000, D000  
Act 4, 5: C000, C800  
Act 6: C000, 1000  
Boss: C000, 2000  