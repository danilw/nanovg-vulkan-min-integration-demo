# nanovg-vulkan-min-integration-demo

**What is it** - this project show Vulkan NanoVG integration to custom render pass. 

### Remember this is not GUI example, NanoVG is UI rendering library

### Contact: [**Join discord server**](https://discord.gg/JKyqWgt)
___

*What you need to do for NanoVG integration* - call `init_nanovg_vulkan(...)` after your full Vulkan initialization, and copy-paste NanoVG render pass after end of your render pass `vkCmdEndRenderPass`.

### This commit [11e4dce](https://github.com/danilw/nanovg-vulkan-min-integration-demo/commit/11e4dceb1acb1b31c19c3c16c7f365f47a42184d) shows NanoVG render pass integration

Can be copy-pasted to any other render pass. (or compare `main.c` to `main_original.c`)
___

As an example of render pass I use my own "single triangle" example Vulkan code from [vulkan-shader-launcher](https://github.com/danilw/vulkan-shader-launcher) (example_minimal there)

*Platform supported* - Windows and Linux (X11/Wayland). 

To build Wayland set `USE_WAYLAND_LINUX` to `ON` in `example_minimal_nanovg/CMakeLists.txt` file.

# Build:

**Use cmake to build.**
```
git clone https://github.com/danilw/nanovg-vulkan-min-integration-demo
cd nanovg-vulkan-min-integration-demo/example_minimal_nanovg
mkdir build
cd build
cmake ../
make
./Vkexample_nvg
```

*Release* [download](https://github.com/danilw/nanovg-vulkan-min-integration-demo/releases/) has example build for Windows and Linux x11/Wayland.

*Hotkeys* - 1 (NanoVG demo hotkey), 2 (set fps to 30), Space pause.

*Launch option* - `--gpu X` (X is 0/1/2 etc) select Vulkan GPU to use, by default selected Discrete GPU.
___

**All changes** in `main.c` **search for** `nanovg Vulkan related functions`

In `demo.c` changed only path to demo files (font/images) to nanovg_vulkan_resources folder.
___

`main.c` - example with integration

`main_original.c` - original single triangle example without NanoVG
___

# Screenshot:

![img](https://danilw.github.io/GLSL-howto/vulkan_sh_launcher/nvg_integr.png)
