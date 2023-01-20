### Flir One for Linux v4l2

Fork of fnoop's cleaned up version. 

Added: <br>
Command line options for:<br>
* Setting the minimum value to a preset temperature
* Setting the maximum value to a preset temperature
* Locking the min and max to the first frame value
* Exponential filter with three speeds (fast, medium, slow) to transition min and max values smoothly
* Turning on/off central crosshair
* Turning on/off max temp locator

Other changes:
* Clipping of data to min and max values to support above
* New Function temperature2raw which performs raw2temperature but backwards

TODO:<br> 
[X] Add some kind of command line parameter parser to expose the setting variables to the outside world<br>
[&nbsp;&nbsp;] Verify its supposed to be using 25 deg C for object reflectivity - this seems like a gross approximation (as we don't yet know the actual temp). Might need an iterative solution starting with 25 C, then refining the answer to get a more accurate solution.

Added Command Line Usage!

<pre>
FlirOne V4L2Loopback
Usage: flirone -p [PALETTE FILE] [OPTION]...
Starts a V4L2Loopback device using the FlirOne Thermal Camera
Requires: LibUSB, loaded V4L2Loopback kernel module with three devices
Load kernel module via 'sudo modprobe v4l2loopback exclusive_caps=0,0 video_nr=1,2,3'


Mandatory Arguments:
        -p [PALETTE FILE]               Specifies the Palette file to use

Optional Arguments:
         -h                             Print this help screen
         -f F|M|S                       Filter max/min limits using Fast, Medium, Slow filter
         -l                             Locks min/max limits to the first frame available
         -H [HIGHTEMP]                  Sets the max limit to HIGHTEMP deg C
         -L [LOWTEMP]                   Sets the min limit to LOWTEMP deg C
         -x                             Enables the centeral measurement cross hairs
         -X                             Enables the max temp coordinate pointer
</pre>


-------------------------------------------

This is a cleaned up version of code posted here:
http://www.eevblog.com/forum/thermal-imaging/question-about-flir-one-for-android/

All credit goes to tomas123, cynfab etc from that forum who did the awesome research and work to make this support.
