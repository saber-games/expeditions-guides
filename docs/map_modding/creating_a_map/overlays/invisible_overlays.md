# Invisible overlays

Sometimes, you need to mark some route within the level (either for yourself or for other modders who you are working on the map with), but do *not* want this route be visible for the player in the game.

For example, you can be creating a map without any roads, but still want to plan some main routes – through forests and rivers – that are possible for the player on this map.

In this case, you can use any overlay for marking this route, but make it invisible by changing the **IsInvisible** option in its properties to **True**.

After rebuilding the map, this overlay will become totally invisible. It will become invisible in the Editor too, allowing you to modify the surrondings and not mixing with them.

However, this overlay will still exist on the map, and, when you want to visualize it, you can enable the **Show all overlays** (![](./media/image36.png)) option on the [Toolbar]. This will highlight it with the blue color and will allow you to modify it easier.


[toolbar]: ./../../getting_started/ui_overview/toolbar_buttons.md