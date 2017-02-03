# UnlimitedLava
[![Build Status](https://ci.dustplanet.de/job/UnlimitedLava/badge/icon)](https://ci.dustplanet.de/job/UnlimitedLava/)
[![Build Status](https://travis-ci.org/timbru31/UnlimitedLava.svg?branch=master)](https://travis-ci.org/timbru31/UnlimitedLava)
[![Circle CI](https://img.shields.io/circleci/project/timbru31/UnlimitedLava.svg)](https://circleci.com/gh/timbru31/UnlimitedLava)
[![Build status](https://ci.appveyor.com/api/projects/status/72ns97g6n7jqy6h2?svg=true)](https://ci.appveyor.com/project/timbru31/unlimitedlava)
[![BukkitDev](https://img.shields.io/badge/BukkitDev-v1.9.3-orange.svg)](https://dev.bukkit.org/projects/unlimited-lava)
[![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue.svg)](LICENSE.md)

## Info
This CraftBukkit plugin aims to offer the same ability to lava that water has:
instant refill, if the block is taken from the middle.
There is a wide range of supported shapes and all these can be changed on the fly.
Special features are
* Lava and water fall support
* Furnace support for (custom) item that should appear if a lava bucket is used as fuel
* Complete permissions support
* Multiworld support

*Third party features, all of them can be disabled*
* Metrics for usage statistics

## License
This plugin is released under the
*Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)* license.
Please see [LICENSE.md](LICENSE.md) for more information.

## Standard config
```yaml
# For help please refer to the bukkit dev page: https://dev.bukkit.org/projects/unlimited-lava
configuration:
  # Should permissions be enabled or not?
  permissions: true
  # Should a message displayed, if a player without the permission picks up lava?
  messages: true
  # Enabled the custom furnace, configure the output of a lava bucket below
  furnace: true
  # At which height (block - not line of sight!) is the lava unlimited
  height: 60
sources:
  # Different sources -> See the schematics below
  three: true
  two: true
  other: false
  big: false
  lava_fall: true
  water_fall: false
  plus: true
  T: true
  ring: true
furnace:
  # What item should appear in the furnace if you place a lava bucket as the fuel?
  item: BUCKET
# Define in which worlds the sources should be unlimited.
enabled_worlds:
  - world
  - world_nether
  - myAwesomeWorld
debug: false
```

## Sources
* `L` are still (full) lava blocks,
* `X` is the unlimited lava block!

#### 3x3 (three)
```
L L L
L X L
L L L
```

#### 2x2 (two)
```
X X
X X
```

#### Plus
```
  L
L X L
  L
```

#### T Shape
```
L X L
  L
```
or
```
  L
L X L
```
or
```
  L
L X
  L
```
or
```
L
X L
L
```

#### Other
```
L X L
```
or
```
L
X
L
```
or
```
L X
  L
```
or
```
X L
L
```
or
```
L
X L
```
or
```
  L
L X
```

#### Big

You can get infinite lava from pools bigger than 3x3 (4x4, 5x5, etc.) from any block inside!
Border blocks won't work!

#### Falls
You can get infinite lava or water from a fall. Just let it flow into a hole and pick it up!

## Commands & Permissions
(Fallback to OPs, if no permissions system is found)

**Please note that __/ulava is just an ALIAS for /unlimited lava__!**
Command alias list
* /unlimitedlava
* /ulava
* /ul
* /ulaba
* /unlimitedlaba

#### General commands
| Command       | Permission node      | Description                         |
|:-------------:|:--------------------:|:-----------------------------------:|
| -             | unlimitedlava.use    | Ability to use the unlimited blocks |
| /ulava reload | unlimitedlava.reload | Reloads the config                  |
| /ulava help   | unlimitedlava.help   | Displays the help                   |
| /ulava status | unlimitedlava.status | Displays the current status         |

#### Enabling or disabling one of the sources or other things
In the following table the X needs to be replaced by one of these values:
* all
* three
* two
* other
* big
* plus
* T
* lava_fall
* water_fall
* furnace
* permissions
* messages

| Command          | Permission node         | Description                 |
|:----------------:|:-----------------------:|:---------------------------:|
| /ulava enable X  | unlimitedlava.enable.X  | Enables source (replace X)  |
| /ulava disable X | unlimitedlava.disable.X | Disables source (replace X) |

#### Special permissions
* unlimitedlava.* - Grants access to ALL other permissions
* unlimitedlava.enable.* - Grants access to ALL enabling permissions
* unlimitedlava.disable.* - Grants access to ALL disabling permissions

## Credits
* loganwm for helping me :)!
* ferrybig for the awesome fall code!
* Xastabus for the new check algorithm!
* You - for using it!

## Support
For support visit the dev.bukkit.org page: https://dev.bukkit.org/projects/unlimited-lava

## Pull Requests
Feel free to submit any PRs here. :)
Please follow the Sun Coding Guidelines, thanks!

## Usage statistics
[![MCStats](http://mcstats.org/signature/UnlimitedLava.png)](http://mcstats.org/plugin/UnlimitedLava)

## Data usage collection of Metrics

#### Disabling Metrics
The file `../plugins/Plugin Metrics/config.yml `contains an option to *opt-out*.

#### The following data is **read** from the server in some way or another
* File Contents of plugins/Plugin Metrics/config.yml (created if not existent)
* Players currently online (not max player count)
* Server version string (the same version string you see in /version)
* Plugin version of the metrics-supported plugin
* Mineshafter status - it does not properly propagate Metrics requests however it is a very simple check and does not read the filesystem

#### The following data is **sent** to http://mcstats.org and can be seen under http://mcstats.org/plugin/UnlimitedLava
* Metrics revision of the implementing class
* Server's GUID
* Players currently online (not max player count)
* Server version string (the same version string you see in /version)
* Plugin version of the metrics-supported plugin

## Donation
[![PayPal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif "Donation via PayPal")](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=T9TEV7Q88B9M2)

![BitCoin](https://dl.dropboxusercontent.com/u/26476995/bitcoin_logo.png "Donation via BitCoins")  
Address: 1NnrRgdy7CfiYN63vKHiypSi3MSctCP55C
