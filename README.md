# Simple install and config for PulseAudio EQ on Raspberry Pi

I simplified an existing guide by pre-creating the additional required files and updating the install steps to use them.
Based on this post by "Vinny" https://www.kubuntuforums.net/showthread.php/73166-Pulse-audio-problem?p=411532&viewfull=1#post411532

We first start by installing PulseAudio EQ
```
sudo apt-get -y install pulseaudio-equalizer
```

Backup existing then download the config file
```
sudo cp /etc/pulse/default.pa /etc/pulse/default.pa.backup
sudo wget -O /etc/pulse/default.pa https://raw.githubusercontent.com/frankpintosr/pulseaudio_eq/master/default.pa
pulseaudio -k && pulseaudio -D
```

Download icon
```
sudo wget -O /usr/share/doc/pulseaudio-equalizer/pulseaudio.png https://raw.githubusercontent.com/frankpintosr/pulseaudio_eq/master/pulseaudioeq.png
```

Download start menu file
```
sudo wget -O /usr/share/applications/paeq.desktop https://raw.githubusercontent.com/frankpintosr/pulseaudio_eq/master/paeq.desktop
```

Restart and enjoy!
```
sudo reboot now
```
