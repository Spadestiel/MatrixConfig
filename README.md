# MatrixConfig
<img src="https://repository-images.githubusercontent.com/282035636/0858ae80-d4ff-11ea-87bb-052579b5239c" width="200px">  

[![Matrix Anticheat](https://img.shields.io/badge/Plugin-Matrix%20Anticheat-%237009ac?style=flat-square)](https://www.mc-market.org/resources/13999)
![GitHub commits since latest release (by date)](https://img.shields.io/github/commits-since/Encode42/MatrixConfig/latest/master?label=Commits%20since%20release&style=flat-square)

[![Support Discord](https://img.shields.io/discord/707330384328654869?color=7289DA&label=Support&style=flat-square)](https://discord.gg/rjSkFyj)
[![Matrix Support](https://img.shields.io/discord/392904793758367745?color=7289DA&label=Matrix%20Support&style=flat-square)](https://discord.gg/rGhYma6)

## About
The optimized config for [Matrix Anticheat](https://www.mc-market.org/resources/13999/), a powerful anticheat for Minecraft.  

This config works for both the free and premium versions of Matrix.  
**Make sure to use the config meant for the version of Matrix you use!**  
<sub>Sometimes Matrix premium updates faster than free, there will be another config file if so.</sub>

#### Features
- Less false positives.
- Better warning messages.
- More strict checks. *(Better detection)*
- Multiple config types to suit your needs.
- Up to date!

## Setup
### Server Usage
1. Download [checks.yml](https://raw.githubusercontent.com/Encode42/MatrixConfig/master/checks.yml), [error.checks.yml](https://raw.githubusercontent.com/Encode42/MatrixConfig/master/error.checks.yml), or [cloud.checks.yml](https://raw.githubusercontent.com/Encode42/MatrixConfig/master/cloud.checks.yml) depending on what you want.  
<sub>For specific Matrix versions, head to the [releases page](https://github.com/Encode42/MatrixConfig/releases).</sub>
2. Rename the original `checks.yml` to something else. `checks.old.yml` will work.
3. Upload/move the checks file to your Matrix plugin folder. (`<server>/plugins/matrix/`)
4. If you downloaded a checks file becides `checks.yml`, rename the new `*.checks.yml` to `checks.yml`.
5. Restart your server!

### Cloud Usage
1. Open `config.yml` in your Matrix plugin folder. (`<server>/plugins/matrix`)
2. Change the line "`- 'your configuration file link'`" (cloud_config.links) to "https://raw.githubusercontent.com/Encode42/MatrixConfig/master/cloud.checks.yml" or any other checks file depending on what you want.  
<sub>For specific Matrix versions, replace `master` with the config version number.

## FAQ
This config may not work perfectly with your server.  
Plugins, software, performance can all effect how well this config and the anticheat in general will work.  
**This is not a drag-and-drop solution! Some values may need to be changed to work best with your setup.**  

Matrix Anticheat isn't a perfect anticheat. It itself has bugs that we cannot fix.  
This config aims to mitigate those issues and improve what works well, but there's only so much we can do.

### 1. Config file types
#### checks.yml
The main config file. Includes the standard checks and everything advertised.

#### cloud.checks.yml
Same as `checks.yml` but minified. It is a lot smaller in file size, but is nearly impossible to read. 
Because of its small file size though, it can be automatically updated fast on server startup.   
This is optimized for cloud usage in `config.yml`. For instructions, read [Cloud Usage](https://github.com/Encode42/MatrixConfig#cloud-usage).

#### error.checks.yml
Same as `checks.yml` but with different kick messages.  
The messages are from classic Minecraft server disconenct messages such as "`java.net.SocketException: Connection reset`" and "`java.net.ConnectException: Connection timed out: no further information:`."

### 2. Suggested changes
1. `nofall.damage: true` -> `nofall.damage: false` (For servers with fall-damage disabled)
2. `speed.tolerance: 0.0225` -> `speed.tolerance: (number from 0.0125 to 0.035)` (Decrease if players are bypassing speed checks)
3. `hitbox.max-reach: 3.2` -> `hitbox.max_reach: 3.3` (If you have issues with the hitbox check)  
<sub>**NOTE**: Makes hitbox detection more lenient! Only change this if you *have* to.</sub>
4. `killaura.modules.autoclicker.max_cps: 18` -> `killaura.modules.autoclicker.max_cps: (number from 8 to 24)` (Lower means less CPS, higher means more CPS)  
<sub>**NOTE**: The highest possible human CPS is 24. This means the number should not be above that as that indicates a macro.</sub>
5. `inventory.cancel_vl: 8` -> `inventory.cancel_vl: (number from 8 to 14)` (Increase if the check causes false positives)
6. `fastuse.commands.24: ...` -> `fastuse.commands.(number): ...` (Decrease if players should be kicked quicker, increase if causes false positives)
7. `block.fastplace.max_place_per_second: 16` -> `block.fastplace.max_place_per_second: (number from 9 to 19)` (Decrease if you think there are bypasses, increase if the check causes false positives)
8. `place.modules.delay.min_delay: 7` -> `place.modules.delay.min_delay: (number 5 to 9)` (Decrease if legit players are getting too many violations, increase if bypassed)

### 3. Why is the anti-killaura NPC spawned in the HitBox check?  
This check also checks if the player isn't using Angle cheats, and the NPC checks if the player can hit people behind the player. To prevent lag and false positives from happening with this, the NPC will be spawned only if the player's ping is lower than 185ms. If I'm right, this should make the killaura detection more strict. [This has been approved by RE](https://github.com/jiangdashao/Matrix-Issues/commit/988e130f60559105cea7ec384e49357864b9f5b4).

### 4. How do I report a change or false positive?
**FIRST:**  
Make sure this isn't an issue with the anticheat itself. Not all issues can be fixed with a config. Head over to Matrix's support Discord and ask about the issue, or report the issue at their issue tracker.  
You can also try using the default config to see if the issue still stands. If so, it's not a problem with the config.  
Matrix's Discord: [Here](https://discord.gg/wjheaRj)  
Issue tracker: [Here](https://github.com/jiangdashao/Matrix-Issues/issues)

**THEN:**  
Make an issue at the issues page with the right template. If you describe what you want changed/fixed well, chances are it'll be taken care of quickly. If you already know what the issue is or how to fix it, feel free to make a pull request containing the change and why you made it.  
Issues: [Here](https://github.com/Encode42/MatrixConfig/issues)  
Pull Requests: [Here](https://github.com/Encode42/MatrixConfig/pulls)  

### 5. Can I modify the config?
Yes! I encourage you do so. You can also distribute it all you want, just please don't claim it all as your own. (Credit the original authors.)
