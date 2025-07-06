# Description

This project is an example of 2d procedural generation in Godot used to create an infinite world of terrains and biomes.

It also overcomes a limitation I encountered with Godot: the auto-tiling system (i.e. [`set_cells_terrain_connect`](https://docs.godotengine.org/en/4.4/classes/class_tilemap.html#class-tilemap-method-set-cells-terrain-connect)) is not performant enough to use at runtime over large chunks of terrain without causing the game to stutter. It's not built for this purpose.

This meant I couldn't smoothly load new chunks of terrain in front of the player to give the sense of an infinite world, which was my goal. To fix it, I implemented my own auto-tiling algorithm to amortize the processing over idle frames, allowing for smooth world generation as you play.

I notice this does run slower in the browser (though still smooth on mine) -- thats okay, the browser version is only a demo. I intend to continue development with this targeting the desktop.
