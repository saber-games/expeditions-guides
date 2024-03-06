# Echo Sounder

*(NEW) This feature is valid for Expeditions only.*


## Overview
The *Echo Sounder* (or *Echolot*) minigame allows the player to scan underwater objects using the *Echo Sounder*.

To successfully pass the minigame, the player needs to locate target models hidden underwater. Every conventional "charge" of the *Echo Sounder* may open the part (of the silhouette) of the underwater model. Using the specified amount of "charges", the player must open the predefined percentage of the hidden models' silhouettes.


## Setup
The general setup of a zone and a stage for this miningame is performed as described in [Minigames: Overview](./minigames_overview.md).

For the *Echo Sounder* minigame, the **MinigameEcholot** settings should be selected in the **setting** field of the *ZonePropertyMinigame* prop.

**NOTE**: Along with the setup of the minigame itself, you should also add a single or multiple target models in the Editor to the area that will be scanned. These models should be *tagged* – i.e., you should specify the certain value in the **Tag** field in the properties of these models in the Editor. The exactly same value of the tag should be specified in the **modelTag** field in the settings of the minigame. Moreover, there are some additional limitations on these target models, see [Important Nuances](#important-nuances) below. 

The **MinigameEcholot** settings are the following:

-   **uiWinHeader** – The text of the header that is displayed in the UI after winning the minigame. If necessary, you can use the standard in-game string here – `UI_DRONE_GAME_WIN_HEADER` which corresponds to *SUCCESSFUL SCAN*. 

-   **uiWinDesc** – The main text is that is displayed in the UI after winning the minigame.

-   **delayWinMs** – Delay of the win popup, in milliseconds.
-   **showTryAgainPopup** – Whether or not should the Try Again popup be shown if the player fails to pass the minigame.
-   **exitSound** – The sound that will be played when the player leaves the minigame. For details on specifying links to sound files, see [Adding Sounds][adding_sounds].

-   **timeToSolve** – The time limit for winning the minigame. If the player exceeds this limit while playing, the minigame is considered failed and closes. In the original game, this parameter is always set to `-1`, which corresponds to unlimited period of time.

-   **name** – The *identifier* of this minigame within this zone that is used by the corresponding stage of the objective. See [Minigames: Overview](./minigames_overview.md) for details.

-   **modelTag** – The tag of target models whose silhouettes the player will "found" during scanning. These models should be added to the scanned area in the Editor and the same value as in **modelTag** should be specified in the **Tag** fields in their properties.

    **NOTE**: There are some additional limitations on these target models, see [Important Nuances](#important-nuances) below.

-   **charges** – The number of "charges" of *Echo Sounder* provided to the player during the minigame. The maximum value of charges is `6`.

-   **scanRadius** – The radius scanned by a single "charge", in meters.

-   **tolerance** – The value in the `[0, 1]` interval that defines the percentage of "covering" of target models' silhouettes by used "charges" necessary to win the minigame. For example, the `0.75` value in this field corresponds to the `75%` coverage – i.e., after players will open the `75%` of the silhouettes, they will win.

    **NOTE**: The value of **tolerance** depends on the settings of the particular minigame. However, the `1` value in this field is not recommended.

-   **scanFxSpeed** – TBD

-   **scanPosHintRadius** – TBD

-   **uiScanHint** – The text of the hint to be displayed in the UI. If necessary, you can use the standard in-game string here – `UI_ECHOLOT_GAME_HINT` which corresponds to *Find all necessary underwater objects by selecting scanning points*.

-   **gamepadMoveSpeedScale** – TBD

-   **inputWinMinigameLink** – *(Not customizable during modding).*

-   **requiredAbilities** – *(Should not be used).*

-   **zones** – In this list, you need to add a record and, in it, specify the link to the zone where the player starts the minigame.

-   **cameraPos** – The position of the camera from which the scanning will be performed by the player. The camera should be looking at the target area from the top. 

    **NOTE**: In the Editor, you can use **Statistics** (![](./../../getting_started/ui_overview/media/image11.png)) button on the toolbar to show the current position and direction of the camera. See [Tip on cameraPos and cameraDir values][tip_on_camerapos_and_cameradir] for details.

-   **cameraDir** – The direction of the camera from which the scanning will be performed by the player. In the original game, `x = 0`, `y = -1`, `z = 0` values or values close to them are used in this field to provide the view from the top.

-   **inputLinkKeyboardOrGamepadMove** – `TBD: This field corresponds to a control (Minigame.ScanPointMove, forward), it should be configured with the default in-game value and hidden.`

-   **selectPointInputLink** – `TBD: This field corresponds to a control (Minigame.SelectPoint). It should be configured with the default in-game value and hidden.`


## Important Nuances

-   This minigame will not work correctly if some parts of target models are outside of the camera view. 

-   You should carefully set up the height of the camera (i.e., **cameraPos**, the `y` coordinate). If the height of the camera is too large, some target models may become hidden due to a large distance to them. Due to this, heights larger than `70` meters are not recommended.

-   Only *static* models should be used as target ones. In the Editor, they are marked as *STATIC*. Dynamic models – marked as *DYN* – should *not* be used as target ones, since they are physical and may disappear when the player drives near them and then away, or hits them. If target models disappear, the player will not be able to pass the minigame. For details, see [Types of models. Collisions][types_of_models]

-   Target models should have a disabled *instancing* in their XML class. The information on instancing is available in the Custom Models guide in the [Custom Level Entities][custom_level_entities] section. 



[tip_on_camerapos_and_cameradir]: ./../../additional_info_on_maps/camera_values/tip_on_camera_pos_and_camera_dir_values.md
[pack]: ./../../packing_and_publishing_maps/packing_maps.md
[types_of_models]: ./../models/types_of_models_collisions.md
[custom_level_entities]: ./../../../custom_level_entities/custom_level_entities.md
[adding_sounds]: ./../sounds_and_music/sounds/adding_sounds.md
