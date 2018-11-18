# vkQuake2
Vulkan port of id Software's Quake 2

Setup:
===
- install Visual Studio 2017 Community (because of MFC and resources)
- install Windows SDK 10.0.17134.0 and MFC in Visual Studio installer

Original code changes:
===
- fixed compiler warnings
- Calling M_DrawTextBox properly without using explicit endframe calls (required for Vulkan)
- added custom debug Windows console for debug builds
- added 1920x1080 screen resolution

Features:
===
- using Vulkan 1.1
- using VK_EXT_debug_utils instead of VK_EXT_debug_report
- updated with Knightmare software renderer with color
- vk_validation command to enable layers (0 - off, 1 - warnings and errors, 2 - full validation, defaults to 2 in debug builds and 0 in release)
- vk_picmip and vk_round_down GL equivalents
- vk_log - redirects layer messages to file
- vk_flashblend - dynamic light drawing control (lightmap or really dynamic)
- vk_finish - basically inserts vkDeviceWaitIdle when necessary - added for completness' sake (a glFinish() equivalent in the original) but really, don't use it!
- vk_lockpvs - equivalent to GL
- vk_polyblend - equivalent to GL
- vk_strings - prints some Vulkan stats
- skipped 8-bit textures - no modern hardware even supports it these days