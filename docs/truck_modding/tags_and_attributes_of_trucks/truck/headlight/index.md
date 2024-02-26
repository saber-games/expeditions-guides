# HeadLight (in Truck)

## Overview
The `<HeadLight>` tag in the [`<Truck>`][truck] section describes the *main light* of the headlights. This light is used to light up the earth and the objects on it.

There can be *only one* such light source for the truck.

Unlike the light sources described in the [`<ModelAttachments>`][modelattachments] section, this light source can illuminate much further. 
And, this light is *not* clipped based on terrain blocks, unlike the light specified in [`<ModelAttachments>`][modelattachments].

All attributes of this `<HeadLight>` tag are the same as attributes of the ordinary [`<Light>`][light] tag. See the desription of the [`<Light>`][light] tag for details.

**NOTE**: Headlights are turned on when the player presses the corresponding button in the game. In the case of the Keyboard, `L` is the default button for enabling Headlights.


## Two `<HeadLight>` tags
Please note that the light of headlights is described in the XML model of the truck in the two different places:

-   The `<HeadLight>` tag in the [`<Truck>`][truck] section – here the *main light* of the headlights is described. 

-   The [`<HeadLight>`][headlight_in_modelattachments] tag in the [`<ModelAttachments>`][modelattachments] section – here the light rays simulation of the headlights (see [`<Model>`][model]) and a flare of the headlights (see [`<Flare>`][flare]) are described, the same way they are described in the [`<StopSignals>`][stopsignals].


[truck]: ./../index.md
[modelattachments]: ./../modelattachments/index.md
[model]: ./../modelattachments/stopsignals/model/index.md
[flare]: ./../modelattachments/stopsignals/flare/index.md
[stopsignals]: ./../modelattachments/stopsignals/index.md
[light]: ./../modelattachments/stopsignals/light/index.md
[headlight_in_modelattachments]: ./../modelattachments/headlight/index.md