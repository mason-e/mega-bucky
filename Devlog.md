# Mega Bucky Devlog

This is my development log for my "Mega Bucky" ROMhack of Bucky O'Hare.

## 7 Jun 2024

Start of development!

### Milestones

#### Font Change

Replaced text chars from mostly Mega Man 2, some additional punctuation from Mega Man 4

- Here is what it looks like before and after the change:  
![game screen](./devlog-screens/log-6-7/1.PNG) ![game screen](./devlog-screens/log-6-7/2.PNG)

#### Life/Power Meters
Made these more "Mega Man"ish. Instead of changing color to indicate fullness, I wanted it to deplete completely. There is one issue with that: In MM, the meters usually have a black outline and black spaces in between, which works because they're rarely put over a black background. But that's not the case in Bucky. One option would've been to give them a fourth color outline, but then it's not possible to give an overall outer vertical boundary - only lines between that would end up showing each "chunk" of the meter. I ended up doing something a bit inexact and having the depleted bars shrink a bit. Original game vs update:
![game screen](./devlog-screens/log-6-7/3.PNG)  
![game screen](./devlog-screens/log-6-7/4.PNG)

## 8 Jun 2024

My second day of development had me hit quickly with the discouraging realization that I may have already exhuasted the easy changes. As a manner of productive procrastination, I played through the game again, recording save states along the way for nearly every screen. While I know the concept of save editors exist, the game is short enough that this was probably much quicker than tracking down or engineering one of my own. It was partly a stalling tactic, but I do think having a quick load into each part of the game is sure to come in handy with the project.

The rest of my efforts were mostly spent poring through the Mesen debugging documentation, although I am not sure I learned much, as the main challenge is making sense of the various hexadecimal values encountered in basically all of the tools.

### Milestones

#### Color Replacement

This is not a permanent change, but an example showing I found how to change the colors. Our heroes in Bucky get a remake in the image of our favorite Blue Bomber. Unfortunately it doesn't work very well. Aside from the color distribution being off, I saw most of the characters' bullets took on the new color as well. The base palettes of the sprites could certainly be changed to make it look better (i.e. Willy and Jenny's shoulders, Deadeye's hat), but I'm not so sure about the bullets being as simple.

![game screen](./devlog-screens/log-6-8/1.PNG)  
![game screen](./devlog-screens/log-6-8/2.PNG) ![game screen](./devlog-screens/log-6-8/3.PNG) ![game screen](./devlog-screens/log-6-8/4.PNG) ![game screen](./devlog-screens/log-6-8/5.PNG)

## 9 Jun 2024

Not much here to demonstrate visually, but a considerable amount learned in sprite editing.

### Milestones

#### Character Sprites

I started identifying the memory addresses of the playable characters' sprites, so far just for their standing and jumping animations.

#### Power Up Sprites

I pulled the equivalent sprites from Mega Man and replaced the 1UP, Power and Life sprites. No screens for now because I eventually reversed course, as it might actually be a pretty big challenge. First is the fact that in MM, they blink in place, but the standard Bucky sprites actually use smaller ones mid-rotation. Secondly, the color palette mapping is gonna be an issue.

## 13 Jun 2024

### Milestones

#### Text Fix

I'm not sure I'll make this a permanent change since I might change the text altogether, but as practice I fixed the "FLYS" typo at the end of the game:  
![game screen](./devlog-screens/log-6-13/1.PNG)

This was not actually as easy it might seem, because there wasn't actually any additional room on that line in the game's ROM. There might be multiple ways to handle that scenario, but what I ended up doing was realizing in the prior screen that "MOTHER SHIP" could be fixed. Thus by removing the space, it freed up room for me to a character, which I accomplished by moving everything back a byte after "MOTHER".  
![game screen](./devlog-screens/log-6-13/2.PNG)

## 15 Jun 2024

### Milestones

#### Tile Replacement

It isn't much, but I made my first attempt at replacing tiles with something from MM. In this screen, I used assets from Blizzard Man's stage (MM6) with slight alterations.  

![game screen](./devlog-screens/log-6-15/1.PNG)

There is still a lot of work that could be done here, such as changing the sky, or making these look like stacks of blocks rather than being continuous.

## 22 Jun 2024

### Milestones

#### Tile Replacement

Added an underwater ice block to match the above surface ones.  

![game screen](./devlog-screens/log-6-22/1.PNG)

## 3 Jul 2024

Technically not any development today, but I started trimming down prior devlog entries to remove most of the detail on techniques used and instead put it in a separate guide.

## 4 Jul 2024

Something I realized is that all Mega Man games have a "square" terrain aesthetic. On my Blue Planet changes I've arleady made, it was fairly easy to replace tiles since that was already square. So I've made it my goal for now to first make levels rectangular before I change the tile aesthetics.

I started out by identifying tiles that are, for example, part of the "taper off" of these cliffs. I replaced them with "G1" in this case (Green Planet Act 1). There will be more, but I'm not going to take screenshots of this going forward, this is just a little demonstration:  
![game screen](./devlog-screens/log-7-4/1.PNG)

My reason for doing this is that these tiles won't be displayed once I fix the terrain to be more square. But in case I need the tile space later on for some other graphics, I didn't want to leave them as-is in ROM, so I changed them to something that will be much easier to find in TLP.

### Milestones

Squared off a lot of Green Planet Act 1. Here's an example, for now I'm going to leave the floating cliffs like that until I replace the graphics with MM ones. I thought this blue/white corner was a bug, but the original palette was like this, so I need to figure out how to change its palette.  
![game screen](./devlog-screens/log-7-4/2.PNG)

## 5 Jul 2024

Today I changed gears and tried to figure out the score. I did find where the score is stored in _RAM_, but I wanted to find it in ROM instead so I could, for example, see if the high score can be set to 0, or change the score value for killing an enemy, but no success yet.

I have a hypothesis that the 50000 (dec) high score value is actually stored as an $05 value somewhere. I wanted to see how often $05s are read from ROM to load in this score, and assume it's either at boot up or start of a level. The value $05 is also used for the letter E in text, so I tried clearing out the game's copyright and title screen text. These aren't exactly how I meant to change them but these are the results:
![game screen](./devlog-screens/log-7-5/1.PNG)  
![game screen](./devlog-screens/log-7-5/2.PNG)

The second screen is notable because I accidentally corrupted the game logo's palette, so I might be able to revisit this to glean how to select palettes.

### Milestones

Not really a milestone, but a more definitive change is one I made in the bottom bar. These letters are nonsense, it was more just for the sake of making sure I could do it - but I kept the change since I have plans for a bigger overhaul here anyway.
![game screen](./devlog-screens/log-7-5/3.PNG)

## 6 Jul 2024

Another day without any big "milestone" progress, but I am furthering my learning on diving into the RAM, and determined where lives, power and health are stored. I also created a repo for this project and started straightening out the documentation.

Revisiting something from yesterday, I tracked down where the title screen logo palette is set. It turns out that was a single byte, and if I change the byte value I can get various results. This does concern me a bit that I might not have as much palette control as I need, but I don't fully understand how this works yet. As seen in the screenshot below, sometimes the palette setting can also screw up the positioning of the text.
![game screen](./devlog-screens/log-7-6/1.PNG)