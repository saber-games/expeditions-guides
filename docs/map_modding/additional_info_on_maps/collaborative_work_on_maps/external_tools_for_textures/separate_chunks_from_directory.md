# Separate chunks from directory

The **Separate chunks from directory** command is also available in the context menu.

This command performs the reverse operation to [**Combine chunks in directory**][combine]:

1.  At the first execution, it creates the `applyTexture` folder within the folder of your level, allowing you to put your modified whole-map-sized textures to it.

2.  After that, at the second execution, it divides all these large textures into smaller ones that correspond to [map pieces][map_pieces] and puts them to corresponding `data\0_0` ... `data\3_3` folders.

**NOTE**: After the execution of this command, all textures in the `applyTexture` folder are removed.


[combine]: ./combine_chunks_in_directory.md
[map_pieces]: ./../map_pieces_their_subfolders.md
