![Logo](logo.png)
# IEO Earth2150 Extensions

### ▶ [Latest Release](https://github.com/InsideEarth2150/EarthExtensions/raw/main/TMP_LS/EarthTmpExtensions.1.0.23.zip)

### Installation
```
~/Game Directory/
   └── Modules/
      ├── EarthFixes.ieo
      ├── EarthTmpExtensions.ieo
      └── EarthTmpExtensions.ini (Optional)
```
### [Features](https://wiki.insideearth.info/wiki/EarthTmpExtensions#Features)

### [Configuration](https://wiki.insideearth.info/wiki/EarthTmpExtensions#Configuration)
#### [Example Configuration.ini](https://github.com/InsideEarth2150/EarthExtensions/raw/main/TMP_LS/EarthTmpExtensions.ini)

### Changelog:
1.0.24:
   - allow mouse wheel zooming inversion (disabled by default)
   
1.0.23:
   - added completed/next research notification
   
1.0.22:
   - added mouse wheel support for scrolling up/down the research tree
   - added mouse wheel support for scrolling up/down the research center (the basic view with 4 tabs)
   - added mouse wheel support for side panels, like builder's production options or fabs production queues
   - added mouse wheel support for bottom panel, like list of buildings, or LC's construction tab
   - added mouse wheel support for chassis/weapon/shield (although shield is never scrollable) selection in Constructor menu (F1)
   - added mouse wheel support for panel with saved units template in Constructor menu (F1)
   - added mouse wheel support for weapon/shield (although shield is never scrollable) selection in Building weapons menu (F3)
   - added mouse wheel support for panel with list of buildings in Building weapons menu (F3)
   - added keyboard arrows support for scrolling up/down/left/right the research tree
   - added keyboard arrows support for scrolling up/down the research center (the basic view with 4 tabs)
   
1.0.21:
   - auto clear/archive Temp and Scripts directories on game start
   
1.0.20:
   - display LC power range
   - extended Solar Power Plant and Mine binds, so that they build Xyrex or Upg. Mine (if researched)
   
1.0.19:
   - auto add chat-channel prefix to sent messages (All/Team/Neutral/Direct)
   
   
1.0.17:
   - new experimental feature of reducing GUI input lag when giving orders (until proves stable, it requires manual activation in the ini file)
   - new custom console commands: "IEO.Ping" and "IEO.LoadObjects"

1.0.15:
   - fixed camera zoom bug in campaigns (thx to Hunter3k0)
   - fixed a bug with blurry textures in constructor menu (introduced in 1.0.13)

1.0.14:
   - added configurable camera movement in earthquake/explosion effect scale factor (reduced from 1.0 to 0.5 by default)

1.0.13:
   - changed file type from .mdl to .ieo
   - added LostSouls support

1.0.12:
   - removed some of the fixes, as they became a part of 2.2.1 core fixes
   - game options adjustments
   - fix for module crashing on clean install of Windows (thx to jmp32)

1.0.9:
   - fix mouse jitter bug
   - add FPS settings
   - disable rendering optimisations for non-D3D renderers, because they crashed (nGlide, OpenGL etc)

1.0.8:
   - fix multi viewport zooming

1.0.7:
   - added smooth zooming

1.0.6:
   - fixed unit/building effects rendering "behind" the object (ie. screamer effect, no power info etc)
