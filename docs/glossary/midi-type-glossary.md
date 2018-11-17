# Midi Type Glossary

This glossary describes each Midi Type message and the parameters/examples to use it.

___

## Empty Message
**Description**

No data will be sent out.

Program Change
**Description**

Sends a Program Change message of a specified number and channel. Program Change messages are usually used to call presets or patches in your Midi devices.

**Example of Use**

Activate a preset/patch on your Midi Device.

## Control Change
**Description**

Sends a Control Change message of a specified number, value and channel. Control Change messages are usually used to change function parameters or call functions in your Midi devices.

**Example of Use**

To activate the record function on the Strymon Timeline, send a CC#87 with any value.
(Refer to Timeline Manual)

## Note On
**Description**
Sends a Midi Note On Message.

## Note Off
**Description**

Sends a Midi Note Off Message.

## Real Time
**Description**

Sends a Midi Real Time message. Choose from Start, Stop or Continue

## SysEx
**Description**

Sends a Midi System Exclusive message. 

The first value is always the length of the SysEx array, followed by the values you want to send. The values are in decimal (base10) format and not in hex. 

The values are spread across multiple messages. For example, if the length of your SysEx message is 5 and the message you want to send out is {0, 4, 25, 54, 23},  you will need to use 2 messages for this SysEx message where:

Msg 1
 * P1/Length = 5
 * P2 = 0
 * P3 = 4

Msg 2
 * P1/Length = 25
 * P2 = 54
 * P3 = 23

The actions assigned to each message must match. For example, if your SysEx message requires using 3 messages on the MC6, the 3 messages need to have the same action i.e. Press.

The length should not include the SysEx start and end bytes (i.e. 0xF0 and 0xF7).

## Midi Clock Tap Tempo
**Description**

Sends a Midi Clock signal to out from USB and 5 Pin Midi. Syncs your Midi Clock enabled devices to a common BPM.

You can set the tempo in the parameters, and then choose if you want the device to show the tap menu.

If selected, the MC6 will load the tap tempo screen when the preset is activated.

If not selected, the MC6 will send out the Midi Clock messages according to the preset tempo. When another event occurs i.e. a switch is pressed or expression is moved, the Midi Clock messages will stop.

## PC Scroll Up
**Description**

Sends an incremental message each time the preset is activated. There are 8 counters in the MC6 internal memory. The Select Slot parameter selects one of this counters for your PC Scroll message. Hence, each time the preset is activated, the MC6 will send a PC message which number is based on that counter. The Increment parameter determines if the counter will be increased each time the preset is engaged. The Lower Limit and Upper Limit parameters lets you set a range where the counter will scroll between.

Let's go through this scenario: If you are trying to scroll through 2 devices (on channel 1 & 2) at the same time with the same preset, first select a counter you want to use. In this example, let's set Select Slot to 1 for Msg1. Increment should be set to Yes, since we want the counter to increase (only for the first message). Thereafter, set your lower and upper limit and channel. For Msg2, select the same slot number as Msg1. Increment should be set to No, since the first message already increased the counter once.

## PC Scroll Down
**Description**

Similar to PC Scroll Up, but counter is decreased instead of increase.

## Bank Up
**Description**

Changes to the next bank on the MC6.

## Bank Down
**Description**

Changes to the previous bank on the MC6.

## Bank Change Mode
**Description**

Puts the MC6 into a state where you can scroll up and down banks with dedicated switches and then select the bank you want to use.

## Set Bank
**Description**

Jumps to another bank on the MC6.

## Toggle Page
**Description**

Toggle between pages in a bank. In the main page, the main switches control Presets A-F. By toggling to the next page, Presets G-L are brought forward to the main page where their preset names will be displayed on the screen, and you can control them with the main switches.

## Set Toggle
**Description**

Changes the toggle state of your presets.You can choose whether to "Set" or "Clear" the toggle positions. "Set" will engage the preset, while "Clear" will disengage it. You can select the presets to apply this change to.

## MIDI Thru
**Description**

Sets the global Midi Thru feature on the MC6 on or off.

## Select Expression Message
**Description**

You can select individual messages in each expression preset to be active with this function. There are 16 messages in each expression preset. If, for example, you set Msg1 and Msg2 to be active on Expression 1, each time you move your expression pedal in Exp1 input, only Msg1 and Msg2 will be sent out.

This setting is global and applied to all banks. It will be reset to all active when the device power cycles.

## Looper Mode
**Description**

This message toggles in and out of Looper mode. Looper mode basically increase the sensitivity of your switches to the maximum, so that messages sent out are instantaneous. This is useful if you are using the MC6 to control time-sensitive functions such as Record/Play/Stop.

In firmware v3.2 onwards, instead of Toggle on/off, we added a selection to allow users to select whether they want to Toggle or set Looper Mode to On or Off.

## Strymon Bank Up
**Description**

Bank up on your Strymon Timeline, Möbius and Bigsky

## Strymon Bank Down
**Description**
Bank down on your Strymon Timeline, Möbius and Bigsky

## AxeFX Tuner
**Description**

Upon engagement, the MC6 will send a CC#15 message with value 127 to the selected channel. CC#15 controls the tuner function on the AxeFX. After which, the tuner page will load. Upon exit, the MC6 will send a CC#15 message with value 0 to disengage the AxeFX tuner.

**Things to note**

Turn off Midi Thru on your AxeFX.

Enable SysEx send on your AxeFX.

Connect your AxeFX Midi out to the MC6 Midi In

## Toggle Preset
**Description**

This setting toggles a Preset between positions 1 and 2, and can be useful if you want to toggle a Preset with a specific action. 

**Things to note**

To use this, be sure to leave the Preset-level toggle setting off. If not, any action engaged on the preset will toggle the preset.