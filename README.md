##CWAudioFileSampler

I originally wrote this class for a drum machine app for iPad, but it could be utilized for any number of applications. 

In use:

See https://github.com/cwalo/PHENOM-RBA for a project utilizing this class.

* Declare an instance of CWAudioFileSampler
* Call ```loadAudioURLS:``` passing an array of audio file URLs
* Call ```loadAUFilePlayers```
* Play a sample by calling ```playSample``` passing an integer for the desired sample.
They will be in the same order passed in ```loadAudioURLS:```. 0 indexed!
* When finished, call ```stopAndClosePlayers```
* To stop all audio, but keep everything in place call ```stopPlayers```


Haven’t tried yet, but you *should* be able to use it for OS X by simply replacing:

```
outputcd.componentSubType = kAudioUnitSubType_RemoteIO;
```
with
```
outputcd.componentSubType = kAudioUnitSubType_DefaultOutput;
```

This class utilizes [Chris Adamson’s](https://github.com/invalidname) AUGraph File Player implementation and his handy CoreAudio error checking method. *Learning Core Audio* is a must-have if you’re just getting into this stuff.

TODO:
* Move away from the array of player AUGraphs and instead have a single AUGraph with dynamically created FilePlayer nodes. Will likely require a Mixer node. This will reduce the overhead and should result in sample-accurate playback.
* Add error checking/handling in ```loadAudioURLS:```

