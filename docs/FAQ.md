# Frequenty Asked Questions

### How do I set an external aux controller to change banks?
Connect an aux controller to the MC6 with a stereo cable. Be sure to change the expression input type to "Aux Switch" in the Main Configuration Menu. The Aux switch will work just like a regular switch, where each switch will invoke a preset. You simply need to program a bank up and bank down message in each preset and you are good to go.

### My MC6 hangs at the main preset screen.
Check your Expression input settings. It is likely that you have your expression input setting set to "Aux Switch" but do not anything plugged into the input ports. If you have nothing plugged into your expression input(s), it should be set to "Expression Pedal" instead of Aux Switch. 

### How do I paste a preset to all banks?
Go into the preset edit menu and then copy the preset. After the preset is copied, hold down the Paste button for 2 seconds. The device will paste the copied preset to all banks for the current active preset.

### How do I set the expression pedal to send different CC messages per preset?
The expression pedal inputs work on a per-bank basis, where every bank has a different expression preset. Each expression preset has 16 midi messages that you can program. By changing banks on the MC6, you can send different CC messages. You can also send different CC messages in each expression preset in the same bank by using your standard presets A-L. By programming a "Select Exp Message" midi type in your preset, you can select which of the 16 midi messages in your expression preset to be active. Hence, when using your expression pedal, only the selected messages will be sent out.