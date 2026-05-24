# Elden Ring: Nightreign

- FPS drops

## On Wayland [NVIDIA]

### FPS drops

Open the game properties

![Properties](img/properties.png)

On the general properties, modify the launch options with the following command:

`PROTON_ENABLE_WAYLAND=1 PROTON_ENABLE_NVAPI=1 DXVK_NVAPI_VKREFLEX=1  PROTON_VKD3D_HEAP=1 %command%`

It'll not fix 100% of the issues, but it'll smooth the FPS drops.
