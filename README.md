# Zone Loading System

This is a zone loading system that automatically takes care for you of all zone loading/unloading/instancing/freeing and attachment to the tree, all that using a background thread to minimize performance hiccups. This allows to have huge game worlds without loading screen.

The zones can be as big or as small as needed, and this can be combined with other optimization methods. If done carefully, the zone transitions will be invisible to the player.

It can be used for indoor and outdoor environments. It can also work for 2D with minor modifications.

![Test image](screenshots/world.png)

- Every zone sits inside a trigger area that completely englobes the zone.
- When the player enters a trigger area, the corresponding zone is loaded, instanced (if not already) and attached to the world.
- When the player exits the area, the zone is removed from the tree but stays in memory, allowing to go back and forth quickly between two zones. When the zone is not directly connected to an area the player is in, it is then freed from memory and unloaded.
- Zones that are connected to the current zone(s) are automatically loaded in memory and instanced in background, so that they are ready when the player enters a new zone. Connected zones are zones that are overlapping the current zone, this is detected automatically, no need to register the connections.

## Pros
- No loading screen during the game.
- Works for 2D and 3D.
- The next zone is loaded in background mode while the player explores the current map.
- Connected zones are automatically detected.

## Cons
- Need to manually split the game world into zones and set triggers.
- Zones need to be carfully designed so that they are occluded when not visible (needs turns and twists).

## Contribute

Please report any issues here: https://godotforums.org/discussion/23868/zone-loading-system
You are free to contribute and improve this demo and do whatever you want with the code, this is a [Creative Commons](https://creativecommons.org/publicdomain/zero/1.0/)

![Test image](screenshots/demo.png)
