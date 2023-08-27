# Reap The Reward
Reap the Reward is a smaller game prototype as a 2D dungeon crawler.

This project was created as a way to test the implementation of enemies controlled with a hierarchical state machine, as well as the implementation of several debugging Editor tools.

![A mock-up of the title screen](./Title-Capture.png?raw=true "Title Screen")

**Playable Link:** https://developer.cloud.unity3d.com/share/share.html?shareId=-ad9zhCLO6Ng114_i7sZmav4CH1xo6W7PDsbow1O4nw

## Controls
WASD or Arrow Keys to move.
- Movement is strictly horizontal
- Press up or W to go through doors
- Press Q to use your sword. 
- Press and hold Q to use a strong attack for double damage (0.75s). This can be used on the ground while stationary or moving.
- Mouse inputs for navigating UI

The player's weapon is still pretty strong (long reach) to balance the tougher enemy AI.

Some tips you should know to beat the level:

1. Illusion "Altars" or green torches: Striking these will break them, which disables green traps, but also spawns enemies.

2. The sword+shield "gladiator" skeleton will defend when attacked. You can counter this defense by either attacking them from behind, or by using a strong attack.

3. You must navigate to the bottom area and open the chest. This will summon the reaper.

4. Once the reaper is summoned, it will continually chase you until you beat the level.

5. When you reach a locked gate in the new area, flip the switch to open it. (And try not to re-flip it which will close it once more).

5. From here, you must navigate back to the beginning of the level to escape.

## Programming and Assets
I wrote all of the code for this project myself. The hierarchical state machine code is based on pseudocode presented in "AI for Games" by Ian Millington.
It took significant modification to work for Unity. Since none of the state transitions are hardcoded, designers or programmers can select functions as callbacks
for enemy behaviours.

The camera also took a lot of time. I modified my original hardcoded implementation to allow for camera areas to be linked in the Editor. The "CameraMap" script
in the project has an algorithm to connect camera areas to make it easier to dynamically update the camera bounds based on the room the Player is in.

I did NOT create any of the sprites. Some of the animations were also preconfigured.
Animators were included for the Skeleton enemies, but all of them were reworked to work for my AI.

See the final section of this readMe for specific credits to asset packages.

## Known Bugs and Limitations
- The camera *still* isn't perfect, it jumps a bit when shifting to new level areas.

- The UI is *still* very basic.

- You can get infinite healing items from hitting certain pots. This was initially just a bug, but I left it in to make things a bit easier.
- I do use object pooling for certain assets, but for food, there is no upper limit to the amount that can spawn, (though they are pooled)

(Hopefully not too much else!)

## Sources
Almost all of the level background sprites
https://assetstore.unity.com/packages/2d/environments/platformer-set-150023

Environmental props, lights, sprites ready for animation
https://assetstore.unity.com/packages/2d/textures-materials/tiles/pixel-2d-castle-tileset-135397

The Hero Character (really impressed with it honestly)
https://assetstore.unity.com/packages/2d/characters/hero-knight-167779

The Enemies (Purchase was worth it imo)
https://assetstore.unity.com/packages/2d/characters/enemy-galore-4-pixel-art-220016

The Gem Sprite asset (Also what I created my first game in Unity with)
https://assetstore.unity.com/packages/2d/characters/sunny-land-103349

The Chest Sprite asset
https://assetstore.unity.com/packages/2d/characters/sunny-land-forest-108124

The Fire Sprite asset
https://assetstore.unity.com/packages/2d/environments/asset-fttgr-free-pixel-art-platformer-222174

The Food assets
https://assetstore.unity.com/packages/2d/environments/free-pixel-food-113523

The Reaper Lightning Effect
https://craftpix.net/product/10-magic-sprite-sheet-effects-pixel-art/?num=2&count=661&sq=magic%20pixel%20sprite&pos=3
