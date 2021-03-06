# Buzzer

Cleanflight supports a buzzer which is used for the following purposes:

 * Low and critical battery alarms (when battery monitoring enabled)
 * Arm/disarm tones (and warning beeps while armed)
 * Notification of calibration complete status
 * TX-AUX operated beeping - useful for locating your aircraft after a crash
 * Failsafe status
 * Flight mode change
 * Rate profile change (via TX-AUX switch)

If the arm/disarm is via the control stick, holding the stick in the disarm position will sound a repeating tone.  This can be used as a lost-model locator.

There is a special arming tone used if a GPS fix has been attained, and there's a "ready" tone sounded after a GPS fix has been attained (only happens once).  The tone sounded via the TX-AUX-switch will count out the number of satellites (if GPS fix).

Buzzer is enabled by default on platforms that have buzzer connections.

## Types of buzzer supported

The buzzers are enabled/disabled by simply enabling or disabling a GPIO output pin on the board.
This means the buzzer must be able to generate its own tone simply by having power applied to it.

Buzzers that need an analog or PWM signal do not work and will make clicking noises or no sound at all.

Examples of a known-working buzzers.

 * [Hcm1205x Miniature Buzzer 5v](http://www.rapidonline.com/Audio-Visual/Hcm1205x-Miniature-Buzzer-5v-35-0055)
 * [5V Electromagnetic Active Buzzer Continuous Beep](http://www.banggood.com/10Pcs-5V-Electromagnetic-Active-Buzzer-Continuous-Beep-Continuously-p-943524.html)
 * [Radio Shack Model: 273-074 PC-BOARD 12VDC (3-16v) 70DB PIEZO BUZZER](http://www.radioshack.com/pc-board-12vdc-70db-piezo-buzzer/2730074.html#.VIAtpzHF_Si)

## Connections

### Naze32

Connect a supported buzzer directly to the BUZZ pins. Observe polarity. Also if you are working with flight controller outside of a craft, on a bench for example, you need to supply 5 volts and ground to one of the ESC connections or the buzzer will not function.


### CC3D

Buzzer support on the CC3D requires that a buzzer circuit be created to which the input is PA15.
PA15 is unused and not connected according to the CC3D Revision A schematic.
Connecting to PA15 requires careful soldering.

See the [CC3D - buzzer circuit.pdf](Wiring/CC3D - buzzer circuit.pdf) for details.
