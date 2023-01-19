### Flir One for Linux v4l2

Fork of fnoop's cleaned up version. 

Added: 
(compile time) options for:
Setting the minimum value to a preset temperature
Setting the maximum value to a preset temperature
Locking the min and max to the first frame value
Exponential filter with three speeds (fast, medium, slow) to transition min and max values smoothly

Other changes:
Clipping of data to min and max values to support above
New Function temperature2raw which performs raw2temperature but backwards

TODO: 
* Add some kind of command line parameter parser to expose the setting variables to the outside world
* Verify its supposed to be using 25 deg C for object reflectivity - this seems like a gross approximation (as we don't yet know the actual temp). Might need an iterative solution starting with 25 C, then refining the answer to get a more accurate solution.

-------------------------------------------

This is a cleaned up version of code posted here:
http://www.eevblog.com/forum/thermal-imaging/question-about-flir-one-for-android/

All credit goes to tomas123, cynfab etc from that forum who did the awesome research and work to make this support.
