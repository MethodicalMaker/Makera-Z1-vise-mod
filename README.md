# Makera Z1 vise mod
A fusion360 project to fix the issues with the Makera low profile vise for the Z1 mill

Place two dowel pins into the machine bed as shown in the image below

<img width="1828" height="1005" alt="vise setup2" src="https://github.com/user-attachments/assets/d13d2f33-4271-4f00-a16c-d1395c7c7832" />

Place parallels or rigid stock material under the vise to elevate it above the machine bed.
clamp the vise down. You can use the screw holes closest to you to aid in clamping. Make sure the vise is not lifting up in the back, as the only available screw holes are located on the near side of the vise base.

Make sure your parallels are not in line with the center or far right screw holes. The mod will also mill two new holes on the left hand side of the vise base, about an inch inward. Your setup should look like the image below.

<img width="1920" height="1080" alt="Still 2026-09-02 200143_1 1 2" src="https://github.com/user-attachments/assets/b033a05d-e523-4c01-9c79-309c87060ff6" />

Use the 3D probe to probe the center of the hole indicated by the arrow. It does not matter if you probe the smaller hole for the bolt, or the wider hole for the bolt head. After, probe the topmost surface of the vise. Since Makera studio does not support only zeroing the Z with the 3D probe, use the following gcode to probe the Z: `G38.2 -Z10` followed by clicking the Z button and pressing set zero, and then jogging the Z axis up so the probe is no longer active.

Validate the speeds and feeds in the fusion360 project. I used a 3 flute 1/8" speed tiger aluminum end mill, so you might need to adjust your settings if you are using a different endmill.

Run the generated gcode.

After the milling has finished, flip the vise base over so the bottom of the base that is normally touching the machine bed is facing upward. You no longer need the parallels under the vise base.

re-zero your machine Z on the vise base, and zero the X/Y on the inside of the newly machined dowel pin hole.

create a chamfering operation that adds a 0.4mm chamfer. This is not included in the fusion360 project, but is very easy to create yourself (I just made a cube of arbitrary size with a 4.04mm hole with a depth of 14.9mm). Use the makera chamfering tool to add the chamfer and break the edge.

Try placing the vise on the dowel pins. If it is too tight, create a bore operation with your cube+hole model, and run that to mill the dowel pin hole again, but this time with the vise base bottom side up. I found that setting the tollerance on the bore toolpath to 0.005mm in the "passes" tab helped the hole mill to the correct size. If it is still too tight, slowly widen the hole 0.01mm at a time.
