# Midi Implementation

Midi implementation chart for the MC6.

___

## PC Messages

PC messages will change the banks on the MC6 MKII, where a PC#0 message will engage Bank 1, and PC#1 message will engage Bank 2, and so on.

___

## CC Messages
The MC6 MKII can be controlled by external midi controllers as well. Send the following messages via another Midi Controller to control the MC6.

| Function | CC# | Value |
| --- | --- | --- |
| Bank Up | 0 | any |
| Bank Down | 1 | any |
| Clear Toggle (All) | 2 | 127 |
| Clear Toggle (Individual) | 2 | 0 - 11 (0 = Preset A) |
| Set Toggle (All) | 3 | 127 |
| Set Toggle (Individual) | 3 | 0 - 11 (0 = Preset A) |
| Engage Preset| 10 - 21 (10 = Preset A) | 0 = Do Nothing |
| | | 1 = On Press |
| | | 2 = On Release |
| | | 3 = On Long Press |
| | | 4 = On Long Press Release |
| | | 5 = On Double Tap |
| | | 6 = On Double Tap Release |
| | | 7 = On Double Tap Hold |
| | | 8 = On Double Tap Hold Release |
