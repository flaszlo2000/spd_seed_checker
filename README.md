# Seed checker
This little patch adds the capability to generate artifact/ring seeds ingame.  
You only need the [original code](https://github.com/00-Evan/shattered-pixel-dungeon), apply the patch and you are set to go.

This feature tries to keep the original balance ideas of the game, i.e. you won't get the full stack of items for all the levels but it only checks for the first level and one artifact/ring (the feature won't tell it's location either).  
Similarly to the "Custom Seed" feature, the seed checker is not unlocked by default, you have to beat the game first (or build it in debug).

![tab image showing the main window in settings](tab.png "main tab")
![tab image showing the main window in settings generating a seed with the unstable spellbook artifact](gen_artifact.png "main tab with artifact seed RCL-NVV-DWQ")
![tab image showing the main window in settings generating a seed with ring of might](gen_ring.png "main tab with ring seed TJW-BFS-GBQ")

# How this works?
The game uses seeded random generators for level generation which is not effected by any other random generation so one can simulate the player's descent and check for the generated items (or basically anything).

# How to apply the patch
Download the patch and the [original code](https://github.com/00-Evan/shattered-pixel-dungeon), apply the patch via git and compile the game as normal. 
On Linux:

```terminal
wget https://raw.githubusercontent.com/flaszlo2000/spd_seed_checker/refs/heads/main/seed_checker.patch
git clone --depth 1 https://github.com/00-Evan/shattered-pixel-dungeon.git
cd shattered-pixel-dungeon
git apply ../seed_checker.patch
gradlew desktop:release
```

If you don't see any differences in the settings tab then most probably you have not beaten the game yet (hence do not have the badge for it which this patch checks).

### Footnotes
You might be able to generate a jar file from this patch alone and add that to the compiled game somehow but I am not a java dev but seen things like this before.  
On the UI/UX side, there's things to imporve, in the future one might add checkboxes/dropdown to check for a concrete artifact/ring but as I see right now, this could prove difficult due to the limited feature-set of the ui lib.  
If you press the seed check button while you are ingame, the program is going to crash. This is intended behaviour and kept as an easter egg.

# Credits
For [Evan](https://github.com/00-Evan) for updating this amaizing game.  
For [Astley](https://youtu.be/dQw4w9WgXcQ?si=XIEXJ39lb5Bt4sk1) for not letting us down.
