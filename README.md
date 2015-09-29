# Battery-Checker-Script-for-mint-ubuntu
A Battery Monitor script for mint/ubuntu os. Once started it polls for every 1 minute. It Checks Battery percentage. If it is less than 75% then prompts a low-battery-sound or if it is greater than 90% then prompts a high-battery-sound. ( You can modify chekpc and chekpc1 parameters in the script to other than 75, respectevely 90 percent)

# Why This Script
I am user of Ubuntu OS. It do not produc any warning sound when battery is low.
It only shows a pop-up that battery is low and connect to power source
When I am reading some pdf or watching video fullscreen then I miss the pop-up and my machine goes to sleep mode.
SO to get rid of that issue I created this script. 
Hope you find this useful.

# Assumptions:
 + A Low-battery-sound.mp3 and High-battery-sound.mp3 is present are /usr/share/sounds/ folder
   + You can download it from http://www.orangefreesounds.com/wp-content/uploads/Zip/Low-battery-sound.zip 
   + Extract the .mp3 file and place it in /usr/share/sounds/ folder
 + `alsamixer` command is supported (i.e. your PC is having ALSA sound card)
   + install it using 
    + `sudo apt-get install alsa`
 + `play` command installed and can play .mp3 files
    + if not installed then install it using
      + `sudo apt-get install sox`
    + add support for .mp3 format using:
      + `sudo apt-get install sox libsox-fmt-mp3`
    
# Get the script
` git clone https://github.com/grevutiu-gabriel/Battery-Checker-Script-for-mint-ubuntu.git`

# Install script and warning sound file

Copy script file and warning sound file in folder:

/usr/share/sound (are required administrative privileges)

# Usage
(Please Don't run it as background process by adding &)

`bash BatteryCheckerScript.sh`

or 

`chmod +x BatteryCheckerScript.sh`
`./BatteryCheckerScript.sh`

or (Best Option)
+ Just double click and set `Run software` as default option.

#Starting with system boot
In order to start running script in the moment of booting perform following steps in Terminal:
`crontab -e`
and add in file that will be opened:
`@reboot bash /usr/share/sounds/BatteryCheckerScript.sh`
then close and reboot computer.

