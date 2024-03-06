# Process of Collaboration: Overview

Using [map pieces][map_pieces] and [chunks][chunks], you can establish a collaboration process that, in general, will be similar to the following:

1.  Leader of the modding team creates an empty new level in the Editor.

2.  Source files of this level are sent to all members of the modding team.

    **NOTE**: These source files, among the other files, will include the `data\0_0` ... `data\3_3` subfolders containing data of all map pieces. These map pieces will be initially the same for all modders.

3.  Team splits the map into chunks and assigns them to members of the team. As a result:

    -   Using the **Select chunk** and **Show zone for work** features, every modder is able to work on the chunk assigned to them only.

    -   Every modder knows the their particular map pieces, i.e. the particular numbered subfloders from the `data\0_0` ... `data\3_3` subfolders set, where the work of this particular modder will be stored.

4.  When it is necessary to update a chunk of the particular modder for all other members of the team, this modder sends their particular map pieces (particular numbered subfloders) to these members. They substitute these folders with folders received from this modder, reload a map from source files, and, after that, these map pieces are updated on their side.

5.  At the end, all map pieces are gathered from corresponding modders and the final building of the map is performed.

**WARNING**: This is the general process without some details. There are some nuances in it – see other topics of this section for info.

**TIP**: To avoid modifications of map pieces that are assigned to different modders, you can set the *Read-only* attribute to `true` for `data\0_0` ... `data\3_3` folders corresponding to these map pieces.

The general process is meant to be similar to the described above. It works precisely this way when you work with:

-   **Terrain** (including all **Geometry** terrain brushes)

-   **Models**

-   **Plants**

-   **Trucks**

-   **References**

However, there are some differencies in this process for working with **Distributions**, **PBR Materials**, **Rivers**, **Overlays**, **Zones**, and **Objectives**, see other topics of this section for details.

[map_pieces]: ./../map_pieces_their_subfolders.md
[chunks]: ./../chunks_selection_of_chunk.md