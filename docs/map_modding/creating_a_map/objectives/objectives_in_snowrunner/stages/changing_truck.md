# Changing Truck

*This topic is valid for SnowRunner only.*  

The group of fields in the **changeTruck** section corresponds to the assignment where the player needs to change their truck to the particular truck.

Similarly to **truckDelivery**, you need to place this truck on the map in Editor, specify its **Id** there, and then specify the same ID in the assignment.

Similarly to **truckDelivery**, you can give the truck involved in the assignment as a reward to the player.

**NOTE**: As opposed to **truckDelivery**, the player can drive the target truck during this assignment.

**WARNING #1**: When creating objectives with multiple stages, you should ***not*** use the **changeTruck** as a stage that goes ***before*** the **truckDelivery** / **truckRepair** stages within the same objective, if you are using the same target truck for these stages. Otherwise, you will block the ability of the player to drive a target truck and he/she will not be able to accomplish the **changeTruck** stage. However, you can use the **changeTruck** as a stage that goes ***after*** the **truckDelivery** / **truckRepair** stages for the same target truck. I.e., you can set an objective for the player to deliver (e.g. using a winch) or repair the target truck, and, then, sit in this truck and drive it. However, you can tell the player to sit into a target truck first and, then, deliver it somewhere or repair it.

**WARNING #2**: In the properties of the target truck (which you require the player to sit into), change **Locked** to **False**. Otherwise, the player will not be able to sit into this truck.

![](./media/image310.png)

**WARNING #3**: You should ***not*** use the **changeTruck** stages within Contests, because they have the default **ChangeTruckFailReason**, which will fail the contest if the player changes the truck.

**WARNING #4**: You should ***not*** use the "**DESTROY**" option in **afterStageFinished** field and/or enable the **Destroy After Substage (Dangerous!)** option in the **changeTruck** assignments.

