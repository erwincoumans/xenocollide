
==================================================================

The XenoCollide algorithm is contained in Collide.h and
Collide.cpp.

A collection of support mapping functions for various shapes is
contained in CollideGeometry.h and CollideGeometry.cpp.

All other files are part of the math library or testbed application.

==================================================================

XenoCollide is available under the zlib license:

XenoCollide Collision Detection and Physics Library
Copyright (c) 2007-2014 Gary Snethen http://xenocollide.com

This software is provided 'as-is', without any express or implied warranty.
In no event will the authors be held liable for any damages arising
from the use of this software.
Permission is granted to anyone to use this software for any purpose,
including commercial applications, and to alter it and redistribute it freely,
subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must
not claim that you wrote the original software. If you use this
software in a product, an acknowledgment in the product documentation
would be appreciated but is not required.
2. Altered source versions must be plainly marked as such, and must
not be misrepresented as being the original software.
3. This notice may not be removed or altered from any source distribution.

==================================================================

Camera navigation controls:

alt-leftmouse	rotate
alt-rightmouse	move forward/backward
alt-middlemouse	pan left/right/up/down

==================================================================

The testbed provides a command-line interface for constructing
shapes and dropping them into a simple rigid body simulation.
For a list of commands, type 'help' at the command prompt.

For a quick taste of XenoCollide in action, type the following
commands at the prompt:

> box 4 6 8
> save mybox

> disc 10
> move 0 0 -5
> disc 5
> move 0 0 5
> wrap
> save mycone

> create 20 mybox
> create 20 mycone
> drop all

You can save commands in a text file in the scripts folder and run them
within the testbed.  Look in the script folder for several samples.

For example, type the following at the command prompt to see multiple
sample shapes:

> run test

==================================================================

Additional Notes:

When making a new shape, the application may hang temporarily
while generating renderable mesh for the shape.  These short pauses
are normal and are not related to the XenoCollide algorithm.

There is a bug in the current version of the testbed that may cause it
to hang indefinitely when generating the render geometry for some
support mappings.  In particular, it has difficulty when shrink-
wrapping tilted discs.  This is a limitation of the convex hull
generator, which I will remedy in a future version of the testbed.

The penetration between objects in the testbed is due to the rigid
body simulator, and not an artifact of XenoCollide.

The rigid body simulator included with the test app is very basic.
It is designed to test a collision algorithm, so it never puts
the objects to sleep and has a very simple contact caching
mechanism.  This leads to occasional jitter as old contacts are
"forgotten" and new ones are established to take their place.

==================================================================

For additional documentation, algorithm details and the latest
source code, please visit www.xenocollide.com

==================================================================

---Gary Snethen

