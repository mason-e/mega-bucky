# Mega Bucky Change List

I wasn't sure what to call this, but I went with Change _List_ rather than Change _Log_ because it is more of a design document than a release note. This is an ongoing list of changes I want to implement/have successfully implemented.

## Categories

I've divided them into categories to help me plan and describe the work. I did my best to divide them in a way that describes both the intended end-user result and the type of development work they might entail. I'm going to keep these flexible and may change the categories themselves at any time, as well as what category something goes into between when it's planned and actually implemented.

These are the categories I'm using, listed roughly in order of easiest to hardest to implement.

### Tile Edit - Simple

This is probably better described with an example - changing the game's text. Sprites are organized in memory as 8x8 pieces, and text is generally a single 8x8. Sprites that can be edited solely in those 8x8 "boxes" fit under this category.

### Minor Script Change

Script changes that fit into the existing available memory (i.e. to fix typos).

### Level Tile Edit

This category encompasses all work to change the tiles that make up a level's terrain and backgrounds. This encompasses changing the tiles themselves, the metatile defintions, the metatile placements and palettes. Most of the changes are in this category.

### Overlay Edit

Not sure what to call this at this point. This would be for editing graphics on the bottom bar, the title screen, cutscenes, etc.

### Sprite Edit

This specifically refers to the look of sprites, their placement in game, etc.

### Gameplay Change - Mathematical

Any change that is purely a change of a value - i.e. an attack's damage, character HP, score values, etc.

### Sound/Music - Simple

Sound effect or music changes that lift it from another game/source.

### Sound/Music - Complex

Sound effect or music changes with an original or remixed sound. I think this is roughly the same amount of technical challenge as the above, but comes with an added creative requirement.

### Functional Change - Smallish

I'm not going to overly categorize gameplay changes until I actually get into them and what is involved. For now, a "smallish" change would be something like adding more enemies to a screen.

### Functional Change - Large

This would encompass anything that requires major changes to the game, i.e. a brand new enemy type, a new game mechanic, a new section of a level.

### Excess

The scope creep, the stuff that goes above and beyond, the things that start to make it feel like a completely different game rather than a hack.

## Proposed Changes

### Tile Edit - Simple

### Minor Script Change
- Press Start instead of Game Start
- Flies instead of Flys
- Thumper instead of Thumber
- Mothership instead of Mother Ship

### Level Tile Edit

New revelation: Achieving a proper MM aesthetic requires minimal palette or pattern table changes. In MM they mostly only change for animations and mini bosses. Sometimes there is a change like when a level goes from day to night. But carrying through the same graphics is important. So this is a mix of old and new notes for now.

#### Green Planet
- Main terrain
    - Make square
    - Similar to MM1 guts man, MM3 hard man, MM6 plant man
- Act 1 (floating platforms)
    - Make sky look more like MM. Get rid of moons - clouds only - and maybe give it a larger mountain background. Blue sky if it still looks dusky.
- Act 2 (tree climb)
    - Transition dusk better. Possible ideas:
        - Can BG palette change after crossing a certain threshold, then not change back if you go back down?
        - What if the stage took place _inside_ an even bigger tree, so sky is unseen?
- Act 3 (river crossing)
    - New tree designs - i.e. MM2 wood man, MM6 plant man
    - New river design
- Act 4 (waterfall descent)
    - Give some depth somehow?
- Act 5 (crossing gunships)
    - See if anything interesting can take advantage of parallax
- Boss - nothing really besides terrain, maybe look of giant rock

#### Red Planet
- Use the Act 1 terrain for all "ground" going forward
- Lava
    - MM1 Fire Man, MM2 Heat man
    - Look for jumping lava/fireballs anywhere
- Act 1-3 (crossing eruptions, caverns, chasing lava)
    - Not sure for terrain, not really any MM volcano level
    - Probably some decent underground MM backgrounds for cavern part
    - Make the act 3 path easier to identify
- Act 4 (jumping lava area)
    - New terrain type, not sure
- Act 5 (spike climb)
    - Change the spike look, make tiles instead of sprites if possible
- Act 6-7 (rocks over spikes)
    - Another new terrain type
    - Rock should at least have a similar equivalent
- Boss
    - Change boss design, considering it's partly tiles
    - Same terrain tiles as 6/7

Notes for the following are much rougher for now.

#### Blue Planet
- Ice blocks over water
    - MM6 blizzard man
    - Need to make colors align in dark background areas
- Robo snakes
    - MM3 Snake Man
    - Bodies altered, need to do head
- Ice floes/bergs over water
- Ice cavern
- Deep cavern with big pushing pistons
- Deep cavern with falling ice and weird blocks
    - MM3 gemini bubbles
- Sewer dumping behind boss

#### Yellow Planet
- Snakes flying out of yellow craters
- Big guns in craters, some overhead platforms
- Gunship climb
- Flying across asteroids/planetoids
- "Rollercoaster"
- Fairly nondescript boss, metal looking platforms from act 2

#### Cell
- Cell Bars
- Triple Guns
    - They are 4x4 tiles, find a similar size in MM
- Conveyor belts
    - MM2 metal man, MM10 sheep man
- Elevators
    - MM5 Gyro Man
    - Each side of the elevator is one metatile wide/tall
- Elevator spikes very similar to MM style "circular" spikes
- Electro things
    - MM3 spark man

#### Salvage Chute
- Green ground, colored pipes, exposed pipes
    - MM2 crash man "pipes"
- Teal bricks and crushers
    - MM1 cut man - probably closet color
    - MM3 wily 1/4
    - MM4 Dust Man crushers
- Weird red pile with bugs, more pipes
- More pipes, pink ground, brain slugs
- Overhead blue spike crushers
- Pipes with lights flickering off
- Red sea with things floating across
- Boss: yellow, sort of brick like ground

#### Magma Tanker
- "Caution" looking crushers
- Mechanical zone with lots of yellow blocks
- Rotating mazes
- Robo snakes over big gaps with purple background
- Boss - red blocks, black background

- MM2 metal man conveyor belts
- MM3 needle man has a similar palette in parts
- MM3 snake man robo snakes

#### Escape
- Gray blocks, flashing colored background
- "Caution" fences over dark background, Marioish tubes
- Mostly black the rest of the way

### Overlay Edit
- Fix palettes for the HUD if possible. Rather be based on character than the stage elements
- Redo the entire bottom bar:
    - Eliminate score
    - Move the life and energy bars to playing field if possible
    - Have character portraits with new space. Or at least have letters B A J D W to indicate selection order
- Stage select screen with Bucky in center, four selectable boxes in a cross shape
    - Up Green Planet, Left Blue Planet, Right Red Planet, Down Yellow Planet
- "Get equipped with" style screen after planet level complete
- "READY" screen instead of planet/act display
    - Even better if "READY" is in-level, but probably more of a gameplay change
- Place the prologue before the title screen rather than after starting a game
    - Have text fade in and out completely rather than scroll
- Remove boot-up copyright info screen

### Sprite Edit
- Make at least Bucky's sprite look more like Mega Man
    - Probably do this with the other characters too, but undecided whether to keep them or to have Bucky absorb their powers 
- Replace power up sprites with equivalents from MM
- Make enemies look more MMish - bigger/cartoonier eyes? This needs fleshing out
- Make the Green Planet collapsing tree branch more obvious

### Gameplay Change - Mathematical

- Make combat HARDER! Across the board changes to enemy HP/damage
    - Boss HP/Willy charge or both definitely need to be rebalanced
- Maximum lives count of 9
- Remove score

### Sound/Music - Simple

- Use sounds from MM: Pause, menu, fire, 1up, level start, etc.

### Sound/Music - Complex

### Functional Change - Smallish

- Eliminate Acts, have (unseen) checkpoints that you go back to on death rather than being able to respawn at every screen
- Game over to beginning of level
- Eliminate life upgrades, always have max health, but max is 28
- Have life bar "fill in" rather than instantaneously go up
- Boss life bars

### Functional Change - Large

- MM sytle "freeze" screen during screen change
    - Hard to implement on its own, but also compounded by the fact many screens in Bucky transition to a completely different style of the level
- Update unfair sections where possible. Needs more fleshing out
    - Cell "Act 5" - conveyor belts on top left return you back to same spot
    - Cell "Act 7" - top path at end takes you back to same spot

### Excess

- "Fix" the Blue Planet. I don't like that it requires a second character to complete. But it might need to be totally different to accomplish that so I'm putting it as excess.
- Putting ladder climbs into vertical sections (or adding new vertical sections)
- Reverse engineer the password system into having some kind of in-game stage select (I mean for ALL eight stages)
- Possible space-saving measures if needed for larger enhancements:
    - Remove demo/credits screens
    - Remove character death sprites, change to MM style "explode"

## Completed Changes

### Tile Edit - Simple

- Changed fonts to match MM
- Changed life/power meter to something similar to MM

### Level Tile Edit

#### Green Planet
- Waterfall styled from MM3 Shadow Man and recolored blue

#### Cell
- Blocks from MM2 Wily 1 Dragon Boss
- Conveyor belts from MM10 Sheep Man
- Single-point spikes from MM4 Drill Man
- Simplified look of star spikes

#### Magma Tanker
- Conveyor belts from MM10 Sheep Man