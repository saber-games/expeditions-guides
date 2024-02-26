# Adding Sound Domains

## Types of Sound Domains
You can add three types of Sound Domains to the map:

-   Regular **SoundDomain** - sets the area where a certain 2D stereo sound will play. For example, using this object we can configure the playback of the water lapping in the swamp.

-   **OneShotSoundDomain** - these domains are designed to play single 3D sounds inside a certain ring around a player when they enter the domain. Sounds will be generated at a random position within this ring. For example, you can configure a sound of the rockfall using this type of domain. When the player drives near a large rock and enters the domain located near it, the player will hear that the sounds of crumbling stones will be played around him/her at a random position with a certain frequency.

-   **NoMusicSoundDomain** - these domains are designed to turn off the in-game music in certain areas. When the player enters the domain of this type, the volume of the music is gradually decreased to zero.

## Adding
All these types of domains are added to the map in a standard way – by right-clicking the **SoundDomains** section in the **Scene View** panel and selecting **Add \<type of the added domain\>** in the context menu.

After that, the domain will be created, and the area of this domain will appear on the map.

## Domain Area
 By default, the area of the sound domain is a square with four vertices.

![](./media/image163.png)

You can edit the domain area in the standard way: move the vertices, add vertices to this area, or delete unnecessary vertices.

To add a new vertex, right-click this domain in the **Scene View** panel and select **Add vertex** from the context menu. Or, if you want to add a vertex at a particular position, you can select a particular vertex of a domain, right-click it, and select **Add vertex** in the context menu. In this case, the new vertex will be added in the middle between the selected vertex and the next one in a clockwise direction.

**NOTE**: If you want the domain to work correctly, *its area must be convex*. If you need to create a domain of a more complex shape, you need to compose it from several convex domains with the same settings.

## Domain Properties
After the setup of the domain area, if the domain is selected, you can configure its properties at the lower part of the **Scene View** panel.

These properties vary for different types of domains. All of them are described in the same section.

### "Sound file" field
For **SoundDomain** and **OneShotSoundDomain** domains, the **Sound file** field sets a [sound][adding_sounds] or a [series of sounds][series_of_sounds] to be played. 

It works the same way as for [regular sounds][adding_sounds]. 


[series_of_sounds]: ./../sounds/series_of_sounds.md
[adding_sounds]: ./../sounds/adding_sounds.md