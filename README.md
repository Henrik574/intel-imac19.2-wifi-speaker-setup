# intel-imac19.2-wifi-speaker-setup
how i was able to fix my wifi, bluetooth, and speakers on my imac 19,2 running ubuntu 24.04.4 LTS

## how i set up wifi

while still on macos, download and run the script from https://wiki.t2linux.org/guides/wifi-bluetooth/
the website's option 3 is what i followed, but it might not work for you.
once you've ran the script on the computer you want to install ubuntu on, you should get a .deb package for linux. i added this file to a usb, but other ways like the ones specified on the t2 linux page will also work.
i then downloaded ubuntu, but if you want to follow the other parts of this tutorial then i recommend either testing it using a bootable usb or just waiting in general.
when you've decided whether to fully install ubuntu yet or just run it live, then on ubuntu you can run the command ```sudo apt install /path/to/firmware_package.deb
obviously, replace the path/to with the actual file path. this will install the wifi firmware. if your wifi still doesnt work, then i dont know what you should try. ask questions somewhere on the internet, a lot of people know more than me about this.


## my bluetooth doesnt seem to be working.

just be patient - the bluetooth should be able to connect natively (without tweaking some part of the system), all of the drivers are there, including for magic keyboards/magic mice.


## how to fix the speakers

the speakers may not work entirely, and when you connect to an external speaker the sound may be considerably choppy.
i ran the commands ```sudo apt-get remove --purge alsa-base pulseaudio
sudo apt-get install alsa-base pulseaudio 

and then checked if my audio worked.
that didnt work, so i added a line of code to the end of the following file: "etc/modprobe.d/alsa-base.conf" file. the line of code to add is ```options snd-hda-intel model=imac27_122
i fixed the external speakers (bluetooth speakers, maybe other cases as well) by adding this line of code to the end of the "
after i ran that, my internal speakers still didnt produce any sound. i couldnt find any other option, so i just bought a permanent speaker for that computer and it has worked fine.

### faq
q: isnt the t2 linux wiki just for macs with t2 security chips?
a: yes, but at least for the wifi/bluetooth portion of the wiki, it includes 19,1 and 19,2 macs as well.
