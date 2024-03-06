# NoMusicSoundDomain Properties

**NoMusicSoundDomain** domains are designed to turn off the in-game music in certain areas. When the player enters the domain of this type, the volume of the music is gradually decreased to zero.

Properties of a **NoMusicSoundDomain** are the following:

-   **Name** - the internal name of the sound domain in the Editor.

-   **Distance threshold** - the distance (in meters) from the domain border, at which the music volume decreases/increases.

-   **Fade in time** - the time (in seconds) for the fade-in transition. This transition will increase the volume of music (from zero to the volume set in the game) when the player is leaving the domain.

-   **Fade out time** - the time (in seconds) for the fade-out transition. This transition will decrease the music volume (from the volume set in the game to zero) when the player is entering the domain.

