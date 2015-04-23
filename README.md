# theraminsim
pythonista theramin simulation

[original code](https://github.com/jsbain/theraminsim)

###background/hints/raisons d'être

From [JonB](https://github.com/jsbain), in [this thread](http://omz-forums.appspot.com/pythonista/post/5887581602447360) at the [pythonista forums](http://omz-forums.appspot.com/pythonista):

>Ok, expanded the simple tone generator a bit into a more fun experiment. A theremin type instrument. Tones are generated in realtime, based on multitouch finger locations. volume is controlled by horizontal axis, tone by vertical. In retrospect one could use the motion library for a more realistic experience, or perhaps introduce other modulation effects, etc.

>The tricky part is keeping the gaps to a minimum. The audio thread generates a short section of the wave every 0.1 seconds. I tried to ensure the wave looks continuous by adjusting that time to ensure an integer number of cycles, and tweaking the sleep time, but that didn't really make a difference, there are glitches at the dt interval. Tweaking this may give more pleasing results on your device.

>This implementation uses an audio thread for each finger, but this makes it lag when many fingers are present. Instead, there should be one audio thread, which takes multiple frequency inputs .

>The `sound.Player` stops playing when the file it was reading gets overwritten, so I had to go to a ping pong buffer system. I have two open wav files, which I switch back and forth between, and have the player playing the file that I already wrote to. These use `tempfiles`, so clean up when the file closes when the thread stops.
