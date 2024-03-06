# Actions. Their Mapping to Buttons

When creating Controlled Constraints or [Powered Constraints](./powered_constraints_overview.md) you can assign particular Actions to them using the `Action` attribute.

Particularly, this attribute exists within the following tags:

-   [`<Group>`](./../../tags_and_attributes_of_trucks/truck/poweredconstraints/group/index.md) of Powered Constraints: `<PoweredConstraints>` → `<Group>` → `Action`
-   [`<Chain>`](./../../tags_and_attributes_of_trucks/truck/poweredconstraints/chain/index.md) of Powered Groups: `<PoweredConstraints>` → `<Chain>` → `Action`
-   `<Constraint>` of Controlled Constraints: `<ControlledConstraints>` → `<Constraint>` → `Action`
-   `<ActionCategory>` used for grouping of control elements in the UI:  
    `<ActionCategories>` → `<ActionCategory>` → `Action`

Every `Action` is identified by its number (from `1` to `14`) and corresponds to the button or a pair of buttons that are used by the player for controlling/activating the constraint:

-   Actions from `1` to `8` – correspond to a *single button*. They can be used for [**Powered Constraints**][powered_constaints_overview] or for selecting ActionCategories in the UI.
-   Actions from `9` to `14` – correspond to a pair of buttons. They can be used for **Controlled Constraints**.

In *SnowRunner*, the particular buttons that are assigned to these Actions can be changed in the **SETTINGS** of the game, in **SETTINGS > CONTROLS > CUSTOM ADDON ACTIONS**.

In *Expeditions*, settings of the game currently do not have this section. Seee **NOTE** at the top of the [Powered Constraints: Overview][powered_constaints_overview] for details.

**NOTE**: Actions from `9` to `14` correspond to the button pairs. And, for every Action of such type, there are two buttons: so-called *forward* and *backward*. However, these names (*forward* and *backward*) are conventional, they do not necessarily correspond to these types of movement, their particular meaning is defined by the Controlled Constraint this Action is used for.

The *default* buttons assigned to Actions are listed in the table below.

| `Action`      | Subaction  | PC |  Xbox            | PlayStation       | Nintendo Switch  | 
|---------------|------------|----|------------------|-------------------|------------------|
| Action `1`    |            | 4  |                  |                   |                  |
| Action `2`    |            | 5  |                  |                   |                  |
| Action `3`    |            | 6  |                  |                   |                  |
| Action `4`    |            | 7  |                  |                   |                  |
| Action `5`    |            | 8  |                  |                   |                  |
| Action `6`    |            | 9  |                  |                   |                  |
| Action `7`    |            | 0  |                  |                   |                  |
| Action `8`    |            | -  |                  |                   |                  |
| Action `9`    | forward    | Q  | Left Trigger     | L2 button         | ZL button        |
| Action `9`    | backward   | E  | Right Trigger    | R2 button         | ZR button        |
| Action `10`   | forward    | W  | Left Stick Left  | Left Stick Left   | Left Stick Left  |
| Action `10`   | backward   | S  | Left Stick Right | Left Stick Right  | Left Stick Right |
| Action `11`   | forward    | A  | X button         | "Square" button   | X button         |
| Action `11`   | backward   | D  | Y button         | "Triangle" button | Y button         |
| Action `12`   | forward    | R  | D-pad Up         | Left Stick Up     | D-pad Up         |
| Action `12`   | backward   | T  | D-pad Down       | Left Stick Down   | D-pad Down       |
| Action `13`   | forward    | F  | D-pad Left       | Left Stick Left   | D-pad Left       |
| Action `13`   | backward   | G  | D-pad Right      | Left Stick Right  | D-pad Right      |
| Action `14`   | forward    | Z  | Left Bumper      | L1 button         | L button         |
| Action `14`   | backward   | X  | Right Bumper     | R1 button         | R button         |

[powered_constaints_overview]: ./powered_constraints_overview.md