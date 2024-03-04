# Visual Inspection

*(NEW) This feature is valid for Expeditions only.*


## Overview
In the original game, the main purpose of the *Visual Inspection* minigame is to show the set of particular objects or viewpoints to the player.

This minigame works as a fly-over of the camera through a certain amount of *Watchpoints*, with the simple "hit the interval" minigame played in between.


## Setup
The general setup of a zone and a stage for this miningame is performed as described in [Minigames: Overview](./minigames_overview.md).

For the *Visual Inspection* minigame, the **MinigameVisuallnspection** settings should be selected in the **setting** field of the *ZonePropertyMinigame* prop.

These settings are the following:

-   **uiWinHeader** – The text of the header that will be displayed in the UI when the player wins the minigame. To display the same text as in the original game, you can use the `UI_VI_GAME_WIN_HEADER` localization string.
-   **uiWinDesc** – The main text that will be displayed in the UI when the player wins the minigame.
-   **delayWinMs** – Delay of the win popup, in milliseconds.
-   **showTryAgainPopup** – Whether or not should the Try Again popup be shown if the player fails to pass the minigame.
-   **exitSound** – The sound that will be played when the player leaves the minigame. For details on specifying links to sound files, see [Adding Sounds][adding_sounds].
-   **timeToSolve** – The time limit for winning the minigame. If the player exceeds this limit while playing, the minigame is considered failed and closes. In the original game, always set to `-1`, which corresponds to unlimited period of time.
-   **name** – The *identifier* of this minigame within this zone that is used by the corresponding stage of the objective. See [Minigames: Overview](./minigames_overview.md) for details.
-   **inputWinMinigameLink** – *(Not customizable during modding).*
-   **requiredAbilities** – *(Should not be used).*
-   **setting** – Settings of the minigame itself. You need to select the *MinigameVisualInspectionSetting* here, it is required.

    -   **successHeader** – You need to specify here the same text or localization string as was specified in **uiWinHeader** above.
    -   **successBody** – You need to specify here the same text or localization string as was specified in **uiWinDesc** above.
    -   **delaySuccessMessage** – The time delay before showing the success text when the player wins the minigame. Typically, it is set to `0`. 
    -   **watchpoints** – The list of interactive and non-interactive *Watchpoints* through which the player passes when playing the minigame, see [Watchpoints](#watchpoints) below. To add a new watchpoint, click plus next to this list.

        **WARNING**: In the **watchpoints** list, there must be *at least* 4 Watchpoints (from `[0]` to `[3]`) totaly. And, from them, there must be *exactly* 3 *interactive* Watchpoints, see below. Otherwise, the player will be able to play the minigame, but will not be able to pass it.


## Watchpoints
Watchpoints do the following: 

-   They set the rules and behaviour for every stage of the "hit the interval" minigame.
-   They set the initial and final (for the stage) positions and directions of the camera, and duration of the fly-over animation between them.

There are two types of Watchpoints:

-   ***Interactive***. These watchpoints require actions ("hit the interval") from the player. **isCinematicOnly** should be `false` for them.
-   ***Non-Interactive***. These watchpoints do not require any actions from the player and set up only the fly-over animation that will be played. **isCinematicOnly** should be `true` for them.

**WARNING**: In the **watchpoints** list, there must be *at least* 4 Watchpoints (from `[0]` to `[3]`) totaly. And, from them, there must be *exactly* 3 *interactive* Watchpoints. Otherwise, the player will be able to play the minigame, but will not be able to pass it.

The mechanics of every watchpoint is the following:

1.  The game sets the camera into the initial (for the stage) position, with the initial direction.
2.  The camera flies over to the final (for the stage) position and direction.
3.  If the watchpoint is interactive, the game allows the player to play the "hit the interval" minigame.


### Watchpoint Settings
The settings of every watchpoint are the following:

-   **isCinematicOnly** – Whether or not this watchpoint is for the fly-over animation only. Should be `false` for *Interactive* watchpoints and `true` for *Non-Interactive* ones, see above.
-   **delayBeforeStartSliderAnimation** – the time delay before the slider will start moving in the "hit the interval" minigame. 
-   **sliderStartFrame** – The delay, *in frames*, before the slider is visualized. Tuning of this delay allows to set up (roughly) the initial position of the slider on the line.
-   **sliderRateModifier** – The multiplier that sets up what *frames* with a slider will be visualized, and, correspondingly, the visual speed of the slider movement. Particulary, `1` means that the slider will be visualized every frame and corresponds to a minimum speed of the slider; `2` means that the slider will be visualized every second frame and its speed will be twice higher, etc. Values starting with `4` are not recommended.   
-   **substractPosition** – The position of the target interval in the "hit the interval" minigame. Along with fixed positions, the list of values contains `RANDOM`, which corresponds to a random position of the interval.
-   **substractDifficult** – The difficulty of the "hit the interval" minigame that corresponds to the length of the target interval.
-   **delayBeforeSubstractShow** – The delay before the visualization of the target interval, in milliseconds. The recommended value is `300`.
-   **delayBeforeSliderShow** – The delay before the visualization of the slider, in milliseconds. The recommended value is `700`.
-   **cameraSettings** – Settings of camera the *internal* zone for this watchpoint. You need to select the *WatchpointCameraSettings* class here, it is required. 
    -   **Duration of transition** – The duration of the "fly-over" animation of this watchpoint, in milliseconds.
    -   **Delay at start** – The delay before the playback of the "fly-over" animation, in milliseconds.
    -   **Delay at end** – The delay after the playback of the "fly-over" animation, in milliseconds.
    -   **cameraPosStart** – The camera position at the beginning of the "fly-over" animation. See [below](#position-and-direction-of-the-camera) for a hint.
    -   **cameraDirStart** – The camera direction at the beginning of the "fly-over" animation. You should specify the direction vector here, e.g. (1, 0, 0). See [below](#position-and-direction-of-the-camera) for a hint.

        **WARNING**: If you leave **cameraDirStart** with `0` values, the animation will not work.

    -   **cameraPosEnd** – The camera position at the end of the "fly-over" animation. See [below](#position-and-direction-of-the-camera) for a hint.
    -   **cameraDirEnd** – The camera direction at the end of the "fly-over" animation. You should specify the direction vector here, e.g. (1, 0, 0). See [below](#position-and-direction-of-the-camera) for a hint. 

        **WARNING**: If you leave **cameraDirEnd** with `0` values, the animation will not work.


## Position and Direction of the Camera
You can identify correct camera positions and directions for watchpoints using the Editor. 

Particularly, you can:

1.  Open the level in the Editor.
2.  In the Editor, move the camera to the necessary point of the level and set its correct direction (roughly).
3.  Show the *exact values* of the current camera position and direction, by pressing the **Statistics** (![](./../../getting_started/ui_overview/media/image11.png)) button on the toolbar or pressing CTRL + T.
4.  Use these exact values when configuring the watchpoint. 

See [Tip on cameraPos and cameraDir values][tip_on_camerapos_and_cameradir] for details.


[tip_on_camerapos_and_cameradir]: ./../../additional_info_on_maps/camera_values/tip_on_camera_pos_and_camera_dir_values.md
[adding_sounds]: ./../sounds_and_music/sounds/adding_sounds.md


