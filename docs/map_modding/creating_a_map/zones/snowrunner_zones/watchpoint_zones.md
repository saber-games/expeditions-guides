# Watchpoint zones

*This topic is valid for SnowRunner only.*  

The **ZonePropertyWatchpoint** property allows you to create a Watchtower (zone), which the player may use to explore the map.

![](./media/image197.png)

The properties of a Watchtower here are the following:

-   **range** - the range of the Watchtower (that defines the opened "explored" area), in meters.

-   **Duration of transition** - Duration of the animation of "observation" (with the camera moving according to the specified camera settings, see below) that will be played when the player selects "Launch Observation" for this Watchtower. The value is specified in milliseconds.

-   **Delay at start** - the delay before the playback of the "observation" animation, in milliseconds.

-   **Delay at end** - the delay after the playback of the "observation" animation, in milliseconds.

-   **cameraPosStart** - the position of the camera at the beginning of the "observation" animation. For details on selecting a correct value for this field, see [Tip on cameraPos and cameraDir values][tip_on_camera].

-   **cameraDirStart** - the direction vector for the camera at the beginning of the "observation" animation. You should specify the direction vector here, e.g. **(1, 0, 0)**, see [Tip on cameraPos and cameraDir values][tip_on_camera]. ***If you leave this field with 0 values, the animation will not work.***

-   **cameraPosEnd** - the position of the camera at the end of the "observation" animation. For details on selecting a correct value for this field, see [Tip on cameraPos and cameraDir values][tip_on_camera].

-   **cameraDirEnd** - the direction vector for the camera at the end of the "observation" animation. You should specify the direction vector here, e.g. **(1, 0, 1)**, see [Tip on cameraPos and cameraDir values][tip_on_camera]. ***If you leave this field with 0 values, the animation will not work.***

[tip_on_camera]: ./../../../additional_info_on_maps/camera_values/tip_on_camera_pos_and_camera_dir_values.md