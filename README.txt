This version of 'Snow' is based off of Splizard's 2013_12_25 release.

I started out making a couple tweaks here-and-there and then it just
progressed into something more complex. Since then several things have been
fixed and a few others added.

There is still more to do.

What follows below is a partial and very rough draft of the README.txt file's
contents. I still have to get my scattered notes sorted to make a better
documentation. If things get too wordy, I'll try splitting them off
into seperate files and see if that makes things easier to consume and maintain.

~ LazyJ, 2014_06_01



~~~~~~~~~~~~~~~~~~~~
List of Changes
~~~~~~~~~~~~~~~~~~~~

INIT.LUA
	* Moved contents to separate lua files
	* Checks for "MoreBlocks" mod



FALLING_SNOW.LUA
	* Falling snow would destroy nodes it deposited snow on. I figured out
that if I switched the 'snow.place' with 'minetest.place_node' and
increased the y position by 2, then the nodes were nolonger destroyed and
the snow would start to pile up.



MAPGEN.LUA
	* Replaced snow:snow with default:snow and snow:snow_block
with default:snowblock.



SLED.LUA
	* The HUD message that displayed when a player sat on the sled would
not go away after the player got off the sled. I spent hours on trial-and-error
while reading the lua_api.txt and scrounging the Internet for a
needle-in-the-haystack solution as to why the hud_remove wasn't working.
Turns out Splizard's code was mostly correct, just assembled in the wrong order.

The key to the solution was found in the code of leetelate's scuba mod:
http://forum.minetest.net/viewtopic.php?id=7175

	* Changed the wording of the HUD message for clarity.



~~~~~~
TODO
~~~~~~

Falling Snow:
* Add code to prevent snowfall from depositing snow on or near torches and lava.

* Add code to prevent snowfall from depositing snow on
'walkable = false' defined nodes.



Sled:
* Figure out why the player avatars remain in a seated position, even after
getting off the sled, if they flew while on the sled.
'default.player_set_animation', where is a better explanation for this and what
are it's available options?


