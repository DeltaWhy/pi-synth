# pi-synth
Raspberry Pi synth - notes and configuration.

## Initial setup
* Raspberry Pi 3
* Raspbian Jessie Lite 2016-05-27
* Korg Taktile 49

1. Write image to SD card
2. `$ sudo raspi-config`
  * Expand filesystem
  * Set up locale, timezone, and keyboard layout
  * Enable SSH server
  * Force audio output to 3.5mm jack if you're not using a USB sound card
3. Reboot to enable new keyboard layout
4. Set up Wi-Fi by editing `/etc/wpa_supplicant/wpa_supplicant.conf`

  ```
  network={
      ssid="your_ssid"
      psk="your_passphrase"
  }
  ```
  
  `$ sudo service networking restart`
  
5. `$ sudo apt update && sudo apt -y dist-upgrade`
6. `$ sudo apt install git`
7. `$ git clone https://github.com/DeltaWhy/pi-synth`

## Experimental setup
Not part of the instrument itself but essential stuff for working on the command line.
```
sudo apt install -y vim tmux
```

## Audio setup
```
sudo apt install --no-install-recommends jackd
```

Be sure to enable realtime priority for JACK.

## TODO
* Look into linux-rt kernel
