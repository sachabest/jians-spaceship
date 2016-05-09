## Jian's Spaceship - CIS 568 VR Project

### [TRAILER](https://www.youtube.com/watch?v=ra4XkazG3OI)
### User’s Guide

* Users must be connected to the Steam service
* The host of the game can press Play on the main menu to start as the pilot
* Joining an open game through the main menu will put the client in the gunner’s seat
* NB: If you are planning on using VR (recommended), you must navigate the menus WITHOUT the HMD enabled. So, please click “Play”, then press ~ to bring up the console, and type “stereo on” to enable the Oculus. You can do the same for joining - just be sure to run “stereo on” after joining a session. 
* The ship’s health is represented by a red bar on a screen above the ship’s viewport. Health is decreased when enemies collide with the ship, and partially restored when the ship flies through the green rings. When health reaches zero, the game ends.
* Enemies can be destroyed using the turret. The turret has limited ammunition, represented by the blue bar above the health bar. When ammo reaches zero, and audible warning will play and the turret will be unable to fire. Ammo is fully restored by flying through one of the green rings.

### Controls

#### Pilot
* Move your hands to the steering wheel, or have your palms face each other to snap the wheel to them, then grip your hands to start controlling the wheel and ship. Release the wheel to brake.
* Push forward while gripping the wheel to pitch down
* Pull backward while gripping the wheel to pitch up
* Turn the wheel left or right to turn
* Recommendation: you may have an easier time controlling if you keep your left hand stationary

#### Gunner
* The red sphere controls the direction of the turret. Grip your right hand near it to have it snap to your position. Then you can move the sphere up, down, left and right and the turret will follow. Release the sphere to stop controlling the turret.
* While you are holding the sphere, a squeezing gesture with your left hand will fire a shot. Each shot will deplete a unit of ammo, visible in the blue bar of the ship’s screen display.

#### Both
* Occasionally part of the ship will break, playing an audio cue and causing sparks to fly out of a component. 
* If the component is a button, simply touch it with leap motion
* If the component is a lever, grip close enough to the handle and pull backward
* Failing to fix the component in a short enough time will slow the ship down temporarily

### Setup and Configuration

* Ensure that leap motion is connected and calibrated
* Ensure that Oculus Rift is using retail runtime 1.3, connected and calibrated
* Must have two players connected to the Steam service to play
* The pilot must press the Play button in the main menu, then the gunner must enter the lobby from the main menu and join the pilot’s game.

### Major Gameplay Features

* Cooperative multiplayer over Steam
* Leap motion ship piloting
* Leap motion turret controls
* Randomized breaking points to be resolved with leap motion
* Randomized goals for the pilot and enemies for the gunner
* Ammo and health regenerates via flying through gates
* Possible VR mode offers immersive experience

### Technical Issues with Leap Motion and Unreal Engine

One of the Leap Motion actor components seems to make the assumption that it isn’t used for multiplayer. If there are two components in the scene, your Leap hardware will control both-- in our case, the gunner motions would also cause the client-side copy of the pilot’s hands to move, causing the ship to move only on the client side. Using a ‘Switch has Authority’ node in blueprints let us work around this issue.

Sacha’s Leap controller hates him

Replication is difficult. The concept and mechanism are not easy to understand. The documentation online doesn’t make too much sense when you read it without background knowledge. Collision detection in a networked environment seems to be very unreliable.

### Plugins and Off-the-Shelf Assets Used in Jian’s Spaceship:

[LEAP Motion plugin](https://github.com/getnamo/leap-ue4) (ships with Unreal but needs to be manually enabled)
