##### LazyJ's Fork of Splizard's "Snow" Mod

This version of 'Snow' is based off of Splizard's 2013_12_25 release.

At LinuxGaming.us, we have been using the Snow mod in our Minetest server for
a year now. I've been tweaking and patching things here-and-there and had a
few ideas. The little here-and-there things progressed into bigger and more
complex changes. Maybe other folks will enjoy these fixes, changes,
and additions.

~ LazyJ, 2014_06_01



Minetest version:  0.4.9
Depends: default
Recommended Additional Mods: MoreBlocks (2014_05_11 or newer)
License:  GPL v2
Source Code:  http://github.com/LazyJ/snow
Download (.zip):  http://github.com/LazyJ/snow/archive/master.zip



~~~~~~~~~~~~~~~~~~~~
List of Changes
~~~~~~~~~~~~~~~~~~~~



##### MapGen

I did *not* fix Snow's mapgen issue with "PlantLife" based mods. That is
far beyond my current skill level.

What little changes I did make were to switch-out Snow nodes that Minetest
now has as defaults (dirt_with_snow, snow, ice). My thoughts being that
texture packs and other mods that use these nodes are more likely
to support default nodes.

I also added a line above and below in the mapgen.lua indicating where to
put the comment symbols to comment-out/disable Snow's mapgen. "PlantLife" based
mods will not produce if Snow's mapgen is active.
*Snow's mapgen is active by default.*
I did not disable it, merely indicated were the comment symbols
are to be placed.

To compensate for the loss of snow resources when Snow's mapgen is disabled,
I created crafting recipes that allows players to craft more snow, ice,
and moss. This not only encourages snow builds, but also allows the
players to create snow biomes where they want and whatever size
they are willing to make them.


##### Fixed
	* Pine saplings are now replaced with tree trunks when the tree grows.
	* Snowballs no longer pass through solid objects. Griefers can no
	longer flood the interiors of builds by throwing snowballs through the
	walls hoping to either leave a snowy mess inside or that a heat source
	would melt the snow and flood the interior.
	* Snowballs no longer destroy nodes when thrown at the sides.
	* Falling snow no longer destroys nodes (same problem snowballs had).
	* Snow bricks now, instead of disappearing like before, melt
	into water sources.
	* Christmas tree saplings once again will drop when pine needles
	are harvested.
	* Dirt_with_snow changes to dirt when a solid, non-light permeating
	(sunlight_propagates) block is set on top of it.



##### Changed
	* All snow and ice stuff (including the stairs, slabs, panels, and
	microblocks) will freeze dirt and dirt_with_grass into dirt_with_snow.
	* All snow and most ice stuff will freeze water into ice, including
	the stairs, slabs, panels, and microblocks. The exception is the
	full-sized ice blocks will not freeze water into ice.
	* Snow brick texture reworked and based off of the default stone brick
	texture (and less purple in the grout).
	* Ice stuff is now semi-transparent.
	* Christmas trees now have blinking lights that give off a
	low-level of light.
	* Christmas tree stars now give off high-level of light and the
	light can be punched on or off.
	* Combined default snow and snowballs. Now snow can be
	thrown (left-click) or placed (right-click). 
	* Snow stuff now has "snow" sounds instead of "grass" sounds.
	* Melting - Full-sized snow blocks, snow brick, snow cobble, and
	ice will melt into water sources (big, permanent mess or portable
	water method if buckets are disabled on your server). Snow (snowballs),
	snow stuff and ice basic stairs and slabs, snow stuff and ice
	circular-saw-made stuff will melt into a water source for 2 seconds,
	switch to flowing water, and then the water dries-up
	(small, temporary mess).



##### Added
	* New block-type: "Snow Cobble". Just like regular cobble and stone,
	snow cobble comes from digging snow blocks.
	* All snow and ice blocks can be crafted into basic slabs and stairs.
	The default slabs stack into full-sized blocks.
	* Soft dependency on a recent release MoreBlocks so all snow and
	ice blocks are compatible with the circular saw. If you don't have
	MoreBlocks installed, Snow will ignore the code for those fancy blocks
	and use basic stairs and slabs instead.
	* All snow and ice stuff works with the screwdriver.
	* Crafting and recycling recipes for snow blocks, ice, and moss.
		* Snow bricks craft-recycle back into 4 snow blocks.
		* 2 snow blocks craft into 3 snow blocks. This is to make up
		for when the mapgen for snow biomes is disabled.
		* 2 snow cobble craft into 3 snow blocks.
		* 4 pine needles craft into 1 moss
	* Snow blocks, snow cobble, and snow bricks can be cooked in a furnace
	to make ice.
	* Snowballs can be thrown (left-click) to build up layers. After the
	eleventh layer, the bottom 9 layers change into a snow block. At a
	very close distance, throwing snowballs can be used as a technique to
	build-up gradual slopes. If you have lots and lots of snow balls, with
	rapid-fire throwing, you can, very briefly, "white-out" another player's
	view if your aim is good enough to hit them in the face.
	* Snowballs can be placed (right-click) but will not stack into
	multiple layers. Just one layer only. Placing snow is more reliable and
	accurate than throwing snow from a distance. By placing snow, players
	are able to create their own, personal, snow biomes.
	* Vertical clearance check for tree growth. The nine blocks above the
	spot where the sapling is placed must be free and clear of all
	obstructions or else the sapling will not be allowed to grow.
	Griefers could place the saplings in builds and when the tree grows it
	may not destroy nodes but it fills the available air space leaving a
	mess for the build's owner to clean-up. Now the trees will only grow
	inside if there is 9, free-and-clear spaces from floor to ceiling.
	* Aliases to help make WorldEdit and "give" commands easier:
			

	"default_snow" = "default:snow"
	"snowball" = "default:snow"
	"snowballs" = "default:snow"
	"snow_ball" = "default:snow"
	"ice" = "default:ice"
	"default_ice" = "default:ice"
	"dirtwithsnow" = "default:dirt_with_snow"
	"snowdirt" = "default:dirt_with_snow"
	"snowydirt" = "default:dirt_with_snow"
	"snowblocks" = "default:snowblock"
	"snowbrick" = "snow:snow_brick"
	"bricksnow" = "snow:snow_brick"
	"snowbricks" = "snow:snow_brick"
	"snowybricks" = "snow:snow_brick"
	"snowcobble" = "snow:snow_cobble"
	"snowycobble" = "snow:snow_cobble"
	"cobblesnow" = "snow:snow_cobble"



~~~~~~
TODO
~~~~~~

Falling Snow:
	* Add code to prevent snowfall from depositing snow on or near torches,
active furnaces, and lava.

	* Add code to prevent snowfall from depositing snow on
'walkable = false' defined nodes.



Sled:
	* Figure out why the player avatars remain in a seated position,
even after getting off the sled, if they flew while on the sled.
'default.player_set_animation', where is a better explanation for this and what
are it's available options?


