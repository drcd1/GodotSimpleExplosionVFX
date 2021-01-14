# Godot Explosion VFX

A very simple way to setup realistic explosions in the Godot game engine that react to lighting.

<img width="75%" alt="Explosion Gif 1" src="demo.gif">
<img width="75%" alt=""Explosion Gif 2" src="demo2.gif">

## Dependencies
- Godot 3.2.3 (https://godotengine.org/)

(and, if you want to create the sprites yourself:)
- Blender 2.80 (https://download.blender.org/release/Blender2.80/)
- Some software to assemble the animation into a spritesheet (I used Texture Packer - https://www.codeandweb.com/texturepacker )

## How to use
- Open the project in GodotFiles/Explosion in Godot.
- Edit properties of the explosion by editing "material.tres".
- Emission Fallof Multiplier and Emission Falloff control how fast the flames disappear.
- Emission Color Ramp allows to modify the color of the flames.
- Smoke Color Ramp allows to modify the color of the smoke.

### How to create your own sprites in Blender3D
0. Open the file smoke_280.blend in Blender 2.80 (more recent versions will not work, as the fluid simulator has been overhauled)

1. Select the domain Smoke Domain in the main scene, go to the physics tab and hit bake.

2. In the outliner, make sure the "Scene" and "AreaLight" collections are enabled, and "normals+" and "normals-" are disabled. Render the animation.

3. In the Render tab, in Color Management, set "Display Device" to "None". In "Film", uncheck the "Transparent" checkbox.

3. Change the render output folder to "normals+", disable the "Area" collection and enable "normals+" collection. Render the animation.

5. Change the render output folder to "normals-", disable the "normals+" collection and enable "normals-" collection.  Render the animation.

### Create a sprite sheet
Use Texture Packer to create 3 spritesheets, one for each of the 3 previously rendered animations.
