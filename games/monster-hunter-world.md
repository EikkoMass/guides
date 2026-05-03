# Monster Hunter: World

- Game crashes after some time

## On Wayland

Open the game properties

![Properties](img/properties.png)

On the general properties, modify the launch options with the following command:

`PROTON_ENABLE_WAYLAND=1 PROTON_USE_NTSYNC=1 %command%`
