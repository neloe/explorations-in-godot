# Observations of the [Action RPG Tutorial](https://www.youtube.com/playlist?list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a)

## Video 1

* Some discussion on stretch modes for pixel type games
* children nodes are relative to parent nodes (epi discovered this during minijam)
* Differences in PhysicsBody2D:
  * static: physal obj no move
  * rigid: physics controls behavior
  * kinematic: have collisions, but movement is controlled with code
* Introduces sprite sheets!
  * Hframes evenly divides the sheet horizontally
* When going to move an object, make sure you grab the correct node (grab Player, not the sprite node)
  * This is why you make sure object's children aren't selectable! 
* Shows how to hide unneeded editor features
* `_ready()` runs when the node is added to the scene
* READ THE DOCS: Makes sense about how things are rendered (essentially `for child in children: child._ready()`)
* `_process_physics(delta)` only called if physics are enabled, but this was done automatically if the method is overridden. This is in the docs.
* Godot docs are wonderful
* Teaches about input
* `position.x += 10` is a big nono; don't manually update position on a kinematic body
* On grid; horizontal movement + is right, - is left
* On grid; vertical movement - is up, + is down
* Explanation of `input_strencth`
* Good explanation of faster diagonal speed.



Video does a good job of showing "if you do this, it's not what you mean to do".

Unanswered questions:

* Is there a best practices for file organization? I'm not a fan of putting the player script with the player 
* Hopefully he answers why he checks !=0 before setting `velocity = input_vector`

## Video 2: delta/smooth movement

* from the YT comments: `move_and_collide` and `move_and_slide` are different. TODO: investigate
* "Changes velocity from pixels/frame to some amount/second"
* Simple explanation of `normalized()`; clamps to 1
* Introduces accel
* Introduces physics: friction (and explains why the check for `!=0`
* Known bug: don't multiply max_speed by delta in clamped
* Don't multiply by `delta` too many times!

## Video 3: collisions + move_and_slide

* Takes suggestions from youtube to use 
* pros and cons to using delta: not using delta makes lag noticeable and player can compensate?
* Good discussion about hit vs hurt boxes
* Shows debug menu: show collision boxes
* Discusses `move_and_collide` vs `move_and_slide`: `move_and_slide` multiplies by `delta` for you
* Shows warnings

Notes:
* Going to be teaching math and physics.  This should be fun!
