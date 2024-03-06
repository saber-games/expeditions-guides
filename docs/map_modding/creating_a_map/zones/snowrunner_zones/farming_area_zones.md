# FarmingArea zones

*This topic is valid for SnowRunner only.*

The **ZonePropertyFarmingArea** property in **props** of a zone marks it a zone appropriate for farming.

However, specifying this property for a zone is *only a part of* more complex setup that is required to enable farming in this zone. 

For details, see the [Farming][farming_overview] section in general and its [Zone for Farming Area][farmning_1_step].

![](./media/image209.png)

**NOTE**: If all other things (see [Zone for Farming Area][farmning_1_step], [Distributions for Farming Area][farmning_2_step], and [Objective for Farming Area][farmning_3_step]) are set up correctly, farming will work even without the **ZonePropertyFarmingArea** property added to the **props** of the zone. However, we still recommend to always add it, since it affects some UI-related use cases (generation of UI text when there is no **Ui Desc** in the farming Stage).

[farming_overview]: ./../../farming/farming_overview.md
[farmning_1_step]: ./../../farming/zone_for_farming_area.md
[farmning_2_step]: ./../../farming/distributions_for_farming_area.md
[farmning_3_step]: ./../../farming/objective_for_farming_area.md