# LinuxTTStoMicGuide
A quick guide (using JACK) to take in speech, convert it to TTS, and pipe audio to an audio input. Works for Ubuntu 22.10 LTS

### Prerequisites:
pavucontrol, jackd, qjackctl, pulseaudio-module-jack, sox, libsox-fmt-mp3

### Configuring JACK:
Settings -> Options -> Execute Script after Startup Click the box and paste "pactl load-module module-jack-sink channels=2; pactl load-module module-jack-source; pacmd set-default-sink jack_out"

If you want to add more audio sinks, add another "pactl load-module module-jack-sink channels=2;" If you want to add more audio sources, add another "pactl load-module module-jack-source;"

### Configuring Pavucontrol:
Pavucontrol should have set the main output device to be the audio sink. Another secondary sinks can be set manually.

### Note:
I don't believe that this setup properly configures the audio input from a real microphone. 
This setup works best on a linux machine. Jack can be setup on Windows, but the start-up commands might not be required. 
Current setup involves a bash script. This might not work as expected on Windows/Mac.

### Reference:
https://askubuntu.com/questions/572120/how-to-use-jack-and-pulseaudio-alsa-at-the-same-time-on-the-same-audio-device
https://gtts.readthedocs.io/en/latest/index.html
