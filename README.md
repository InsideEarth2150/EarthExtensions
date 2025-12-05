![Logo](logo.png)
# IEO Earth2150 Extensions

### ▶ [Latest Release](https://github.com/InsideEarth2150/EarthExtensions/raw/main/TMP_LS/EarthExtensions.2.11.0.zip)

### Installation
```
~/Game Directory/
   ├── discord_game_sdk.dll
   └── Modules/
      ├── EarthExtensions.ieo
      └── EarthExtensions.ini (Optional)
```
### [Features](https://wiki.insideearth.info/wiki/EarthTmpExtensions#Features)

### [Configuration](https://wiki.insideearth.info/wiki/EarthTmpExtensions#Configuration)
#### [Example Configuration.ini](https://github.com/InsideEarth2150/EarthExtensions/raw/main/TMP_LS/EarthExtensions.ini)

### Changelog:

2.11.0
   - more gamespeed options in skirmish (up to +10000%, if your PC can handle it)
   - joining a lobby displays 7 last characters of your game parameters hash

2.10.0
   - fixed Temp/Scripts directories cleanup - the files will be now properly deleted
   - added logging of some more memory usage data in crash logs that can potentially help in diagnosis of some memory issues on Linux
   - automated group control creation is now available not only from the factory level, but globally in the constructor (F1) panel.
   - it is now possible to set mouse sensitivity below minimum (new config parameter "MouseSensitivityModifier", default 0.2125, which scales mouse sensitivity globally)
   - (advanced) extended anim button parameters configuration, which alters the way rotating buttons are displayed. "Modifier" options allow applying constant value to the parameter, while "Scale" options multiply the original mesh value. New config options:
      - AnimButtonPositionXModifier (default 0.0);
      - AnimButtonPositionXScale (default 1.0);
      - AnimButtonPositionYModifier (default 0.0);
      - AnimButtonPositionYScale (default 1.0);
      - AnimButtonPositionZModifier (default 0.0);
      - AnimButtonPositionZScale (default 1.0);
      - AnimButtonPositionAlphaModifier (default 0.0);
      - AnimButtonPositionAlphaScale (default 1.0);
      - AnimButtonPositionBetaModifier (default 0.0);
      - AnimButtonPositionBetaScale (default 1.0);
      - AnimButtonRotationAlphaModifier (default 0.0);
      - AnimButtonRotationAlphaScale (default 1.0);
      - AnimButtonRotationBetaModifier (default 0.0);
      - AnimButtonRotationBetaScale (default 1.0);
      - AnimButtonRotationPhiModifier (default 0.0);
      - AnimButtonRotationPhiScale (default 1.0);
   - option to disable animation rotation speed fix (ApplyAnimationRotationFix) is no longer available. Instead, one can achieve the same with the configuration above, by setting `AnimButtonRotationAlphaScale = your_desired_fps/20`, for isntance, `AnimButtonRotationAlphaScale = 9.0` for 180 FPS
   - it is no longer possible to accidentally place artillery with "small tower" shortcut (technically it was possible if you researched artillery as LC without researching Nests)
   - Medium Defense shortcut now builds "A3 towers" instead of weaker "Large towers" if both are available
   - research tree size can be now configured. Used to be `SmallerResearchTree` config option, that could toggle between original (4 rows) and smaller (8 rows, default) version. This option is no longer available. Instead, you can specify the exact amount of research tree rows that you want to see with `ResearchTreeRows` config parameter (default 8)
   - another attempt (this time hopefully successful) to fix scoreboard music getting cancelled

2.9.0:
   - new stats metrics:
      - builders count
      - suppliers count
      - military units in combat (shown as percentage of all units)
      - experience level (shown as average unit level)
      - shadow unit coverage
      - banner unit coverage
      - factories count
      - repaired HP
      - CR value of repaired HP
   - own and ally factories present information about current and next queued production
   - EarthNet and MP lobby now have dedicated music
   - fixed bug in color glow calculation (introduced in 2.4.0), that caused incorrect display of objects with high temperature
   - saved research center tab selection will be reset when game ends (avoiding the "UCS EQ rush" trap)
   - random positions checkbox reduced in width by 50% (what makes it harder to select by accident)
   - research center tree view is now 2x smaller (2x more elements are displayed)
   - interface scaling - x0.75 by default
   - fixed broken "Random positions" algorithm, which was making positions only partially random
   - crash logs store flag about Wine usage (which indicates Linux OS)
   - excluded "Change script" popup from autoclosing when selection changes

2.8.0:
   - fixed mass production lag issues in MP games
   - changed Mass Production button primary behaviour, added 1 new option - see in game tooltip for details
   - game logs damage/kills dealt by mines (they are not being assigned to instigating minelayers unfortunately)
   - fixed subbuildings order getting mixed for MDW in "Select next object" shortcut
   - crash logs now log memory usage information

2.7.0:
   - made player colors on the minimap brighter
   - minimap terrain colors can be switched to grayscale
   - new stats metrics: buildings under construction, number of operating mining entities and number of research centers
   - extended Discord integration - Discord now shows "EarthNet", "Multiplayer lobby" and "Spectating a game" states
   - fixed weapons rendering bug in F2 panel
   - entering lobby displays more info about the player (all MP-relevant modules are listed)
   
2.6.0:
   - support LC walls in "Select next object" shortcut
   - editor fixes/enhancements
      - fix max zoom resetting to default every time you close the game
      - removing tunnels no longer removes passives on the surface
      - placing trees, stones etc no longer removes objects/artifacts in the tunnels
      - fixed disappearing "\[?\]" button in some language+resolution configs
      - editor now plays random day/night music instead of menu music
   - all structures show "Kill count" (not only defensive ones and MDW)
   - enhanced unit selection options
      - "Select all ground units" got replaced with "Select all air support units" (phoboses, scouts etc)
      - "Select all air units" got replaced with "Select all air military units"
      - "Select all military units" got replaced with "Select all ground military units"
      - "Select all civil units" got replaced with "Select all ground support units" (civil units with banners, shadows, radars)
      - "Select all ground military units" includes ground support units by default
   - new stats metric - "Commands sent"
   - creating a dedicated profile for replaying demos should no longer be needed
   
2.5.1:
   - new Ieo.EarthNetReset command that resets login and password stored for the current profile

2.5.0:
   - display notification in chat when you receive unit(s) or money from other player
   - auto-accept all incoming alliance offers within first 30 seconds of game - no more alliance popups in early game
   - change taiga source/destination markers into more distinguishable yellow circles used by harvesters
   - second fix to next idle builder/harvester shortcut, that could still select wrong unit in 2.4.0
   - building info panel (bottom right text, previously altered in 1.26.0) changes:
      - fixed panel not refreshing at times
      - show % progress on "Next researches" list
      - show "Next researches" list for own research centers too (used to be only on allies)
      - fixed power calculations for batteries (the in/out energy would display improperly during partial/total blackouts)
      - fixed power plant produced/consumed energy displays, so that it doesn't take battery input/output into account, what led to showing useless and redundant data for LC

2.4.0:
   - fixed next idle builder/harvester shortcut, so that it doesn't select a unit that already received an order (lag dependent)
   - selecting mine/refinery/supply center/taiga/harvester/supplier highlights related objects (for example, selecting UCS refinery highlights assigned harvesters). The feature is enabled by default and is configurable as: ON (always on)/OFF (always off)/HOTKEY (shown on held ALT).
   - QuickRecord can be set to toggle mode (instead of hold/release). Configurable, disabled by default.
   - fixed display of progressbars on scoreboard

2.3.0:
   - added new shortcut (replaced existing "Go to next unit") - "Select next object of the same kind". The shortcut allows toggling between buildings/units of the same kind
   - fixed/enhanced select next idle builder/harvester shortcuts, so that the closest unit gets selected. The mechanism attempts to ignore units that are stuck/blocked etc
   - extended format of stats files - 2 new metrics and detailed summary info for each unit
   - demo player - it is finally possible to replay recorded games
   - multiplayer game lobby displays player colors
   - game lobby enhancements - elements were rearranged, dropdowns size got increased
   - added "Kill count" display for defensive structures, artillery and MDW.
   - fixed a bug for the largest brush size of average function in editor
   - optimization: certain visual effects stop being rendered past some distance from the camera

2.2.0:
   - new mass production queue button available from within Constructor panel
   - AnimButton/MeshButton rotation speed fix can be now disabled in configuration if needed

2.1.0:
   - (!) broke compatibility with versions before 2.1.1.1 (singleplayer) and 2.2.1.3 (multiplayer)
   - changed name of the module from EarthTmpExtensions.ieo to EarthExtensions.ieo
   - Discord integration - Discord now correctly detects the game without need to manually select exe etc. Discord status displays more details about your in-game actions
   - fixed rendering artifacts appearing on larger zoomouts
   - extended crash logs, again - added logging of all loaded libraries
   - join lobby messages - when a player joins lobby, a message gets displayed, along with random seed of the player. Players with different random seed will most likely cause a desynchronisation, so it is a way to spot it early.
   - enabled starting multiplayer games without any other players or even AIs. That way you can train in MP mode (there are small differences), or even record demos of your solo games (since they are technically multiplayer games).
   - minimap is refreshed every frame what makes it look much smoother
   - editor GUI enhancements - larger brushes for texturing/terrain modification
   - editor fixes - fixed the mechanism of trees/rocks generation that not only failed to be random at times, but could also crash the game, fixed a few more crashes (Average function for terrain, placing resources near level margin)

1.28.1:
   - fixed spectators crashing if they attempted to use new shortcuts introduced one version before (select next builder/mining unit)
   - demo/replay recording of multiplayer games (no playback yet)
   - stats recording - every multiplayer and skirmish game generates a stats file that can be later viewed in the stats viewer app
   - extended logging - each crash goes to a separate file, more info is logged, screenshot is taken (if possible)
   - temp files are not archived by default but permanently deleted, as the game kept on reading them from the archive directory

1.27.0:
   - fixed FPS calculation on some intel CPUs (the `display.show 1` command)
   - adjusted AnimButton/MeshButton rotation speed to the Desired FPS (fix for fast spinning blueprints)
   - rendering optimizations (5%-20% FPS improvement)
   - increased max game speed for single player (up to 1150%, default was 150%)
   - change speed messages display the current speed in %
   - fix for false desync alarms when transferring/capturing units
   - added `/shrug/`, `/tableflip` and `/unflip` chat emojis known from Discord
   - new hotkeys/shortcuts (replacing "Select platoon" shortcuts in game options):
      - toggle building power
      - sell building
      - select next idle builder
      - select next idle mining unit (Taiga/Harvester)

1.26.0:
   - multilanguage (EN/DE/PL/RU) support for custom labels
   - fixed research translation mechanism that could potentially lead to a crash
   - extended selection info for batteries and MDW structures
   - enabled selection info for allied structures
   - extended allied structures' selection info by current money (for mine and refinery) and current research (for research center)
   - extended game crash logging
   - desync detection for multiplayer games

1.0.25:
   - prevent cancellation of recording mode by dragging mouse (accidental queue cancellation)
   - added custom building icons - configurable: ON (always on)/OFF (always off)/HOTKEY (shown on held ALT):
      - idle/snooze icons for buildings if they are not in working state (all fabs, mines, research centers, loaded MDWs)
      - progress icons for all ongoing productions, researches, charging of MDWs and LC batteries (shown with ALT key by default)

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
