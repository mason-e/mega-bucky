# Mega Bucky Change List

I wasn't sure what to call this, but I went with Change _List_ rather than Change _Log_ because it is more of a design document than a release note. This is an ongoing list of changes I want to implement/have successfully implemented.

## Categories

I've divided them into categories to help me plan and describe the work. I did my best to divide them in a way that describes both the intended end-user result and the type of development work they might entail. I'm going to keep these flexible and may change the categories themselves at any time, as well as what category something goes into between when it's planned and actually implemented.

These are the categories I'm using, listed roughly in order of easiest to hardest to implement.

### Sprite Edit - Simple

This is probably better described with an example - changing the game's text. Sprites are organized in memory as 8x8 pieces, and text is generally a single 8x8. Sprites that can be edited solely in those 8x8 "boxes" fit under this category.

### Sprite Edit - Complex

This is like the above, but for larger sprites, or sprites where the color palette needs to be changed. By that I mean the actual colors as they appear in game, not the "master" palette.

### Script Change

Pretty self-explanatory - change to the game's script, i.e. for clarity, fixing mistakes, or just to rewrite entirely.

### Gameplay Change - Mathematical

Any change that is purely a change of a value - i.e. an attack's damage, character HP, score values, etc.

### Sound/Music - Simple

Sound effect or music changes that lift it from another game/source.

### Sound/Music - Complex

Sound effect or music changes with an original or remixed sound. I think this is roughly the same amount of technical challenge as the above, but comes with an added creative requirement.

### Aesthetic

This category would include any changes that don't affect gameplay/sound but require more than sprite editing. An example would be moving a health bar to a different part of the screen.

### Gameplay Change - Smallish

I'm not going to overly categorize gameplay changes until I actually get into them and what is involved. For now, a "smallish" change would be something like adding more enemies to a screen.

### Gameplay Change - Large

This would encompass anything that requires major changes to the game, i.e. a brand new enemy type, a new game mechanic, a new section of a level.

### Excess

The scope creep, the stuff that goes above and beyond, the things that start to make it feel like a completely different game rather than a hack.

## Proposed Changes

### Sprite Edit - Complex

- Make at least Bucky's sprite look more like Mega Man
    - Probably do this with the other characters too, but undecided whether to keep them or to have Bucky absorb their powers 
- Replace power up sprites with equivalents from MM
- Make enemies look more MMish - bigger/cartoonier eyes? This needs fleshing out
- Make levels look more MMish. Needs fleshing out, lots to lift from (i.e Green Planet > Wood Man)
- If possible, fix the palettes for the HUD elements so they don't change
    - Health/energy based on character is okay, just not by stage elements

### Script Change

### Gameplay Change - Mathematical

- Make combat HARDER! Across the board changes to enemy HP/damage
    - Boss HP/Willy charge or both definitely need to be rebalanced
- Maximum lives count of 9

### Sound/Music - Simple

- Use sounds from MM: Pause, menu, fire, 1up, level start, etc.

### Sound/Music - Complex

### Aesthetic

- Stage select screen with Bucky in center, four selectable boxes in a cross shape
    - Up Green Planet, Left Blue Planet, Right Red Planet, Down Yellow Planet
- "Get equipped with" style screen after planet level complete
- "READY" screen instead of planet/act display
    - Even better if "READY" is in-level, but probably more of a gameplay change
- Place the prologue before the title screen rather than after starting a game
    - Have text scroll automatically at a fixed rate, but make entire scene skippable
- Remove boot-up copyright info screen
- Have life bar "fill in" rather than instantaneously go up
- Boss life bars
- Life and power bars overlaid in game instead of lower HUD
- Change lower HUD to character portraits

### Gameplay Change - Smallish

- Eliminate Acts, have (unseen) checkpoints that you go back to on death rather than being able to respawn at every screen
- Game over to beginning of level
- Eliminate life upgrades, always have max health
    - Contingent of course on implementing harder measures to counteract this

### Gameplay Change - Large

- MM sytle "freeze" screen during screen change
    - Hard to implement on its own, but also compounded by the fact many screens in Bucky transition to a completely different style of the level
- Update unfair sections where possible. Needs more fleshing out

### Excess

- "Fix" the Blue Planet. I don't like that it requires a second character to complete. But it might need to be totally different to accomplish that so I'm putting it as excess.
- Putting ladder climbs into vertical sections (or adding new vertical sections)
- Reverse engineer the password system into having some kind of in-game stage select (I mean for ALL eight stages)
- Possible space-saving measures if needed for larger enhancements:
    - Remove demo/credits screens
    - Remove character death sprites, change to MM style "explode"

## Completed Changes

### Sprite Edit - Simple

- Changed fonts to match MM
- Changed life/power meter to something similar to MM