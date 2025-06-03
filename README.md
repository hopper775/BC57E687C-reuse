# BC57E687C-reuse
attempt at reusing BC57E687C based module from SONY sound bar

Looks like this:
![IMG_20250603_210427361](https://github.com/user-attachments/assets/322ceb1b-6371-426a-953e-6d3e07f00113)

Sound bar model: SA - CT260H

![IMG_20250603_175335](https://github.com/user-attachments/assets/765bead5-d470-46d4-a7c6-a5800219f833)

The module communicates with the rest of sound bar using UART.

So far i have captured the UART data when the sound bar is first turned on, after the pair button is pressed and when dvice is connected.

Result of that is
1. Module sends this at 115200 after first power up:
   
INITOK

VER=107

PWR=1

2. I can pair new devices by sending "AT+PAIR=0" to the UART, number doesn't seem to matter, i it works regardless of what i put there (tried 0, 6, 60), in return i get "PAIR=4"(4 is probably the total number of paired divices).
3. If it does not "understand" what the comand is it thows "ERR=11" but only if part of the comand is somawhat correct(does not respond to complete gibberish, for examle it responds to "AT+" and nothing for "ABC=1")

After pairing and conecting i can play audio and it outputs it on spdif out, witch is totally useless for me... nothing  on analog outputs(not surprising).
