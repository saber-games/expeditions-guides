# Upgradeable Garage 

*This topic is valid for SnowRunner only.*  

If necessary, you can set up a repairable (upgradeable) Garage whose functionality the player will gradually enable by accomplishing various objectives, as a reward for them.

This process has three steps, see below.

## Step 1: Select initially available functionality
First of all, you need to specify what functionality of a Garage will be initially available for the player.

This can be done by enabling and filling in the **Upgradeable Garage State** section of the **ZonePropertyGarageEntrance** zone:

![](./media/image192.png)

The check boxes in the **Upgradeable Garage State** section correspond to different functionality areas that are initially enabled for the player in the Garage. By disabling them – you disable the corresponding functionality at the start.

## Step 2: Configure objectives
Then, you need to configure one or more objectives that will activate certain functionality areas of a Garage as rewards for their accomplishment.

Particularly, when setting up an objective, in the **rewards** field, add the **ObjectiveRewardsUpgradeGarage** section and fill it in. Particularly, fill in the following fields there:

-   **Garage Entrance Zone** – the zone of the upgradeable Garage (where you have disabled some functionality at Step 1).

-   **Feature To Unlock** – the particular (previously disabled) feature of the Garage that you want to enable as the reward for the accomplishment of this objective.

![](./media/image193.png)

If necessary, you can add multiple such **ObjectiveRewardsUpgradeGarage** sections in **rewards** of a single objective or configure multiple such objectives.

## Step 3: Modify Terrain properties
Finally, you need to specify that you will be using upgradeable Garage on your map in **Terrain** properties.

Particularly, you will need to enable the **Use upgradeable garage** option in the properties of **Terrain**:

![](./media/image194.png)

**WARNING**: If this option is set to **False**, the upgradeable Garage will not work properly and there will be several issues with it (the black screen inside the Garage, vehicles "sticking" to terrain when leaving Garage, and, sometimes, even crashes). So, please do not forget about enabling this option when setting up the upgradeable Garage.

**NOTE**: However, by default this option is disabled, for memory optimization reasons. It should be enabled on maps with upgradeable Garage only.

