# NetSync

The `<NetSync>` tag sets up the synchronization of the multiplayer.

By default, positions and speeds of all bones of the physical model are transferred from the remote vehicle. However, such synchronization can be disabled in this tag. After that, only the bones (`Body`) with the `pv` value of the `NetSync` attribute (`NetSync="pv"`) will be synchronized.

Attributes:

-   `Legacy="false"`  
    Synchronization of all bones of the physical model. By default: `true`.


