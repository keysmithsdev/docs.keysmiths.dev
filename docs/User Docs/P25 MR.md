# P25 MR

P25 MR mode allows the adapter to emulate a target radio, in order to extract keys from an existing keyloader (e.g. Motorola KVL, Christie TKMD).

To use the emulator functionality, first connect the target keyloader to your adapter using a suitable cable. The cable should be straight through, connecting the data and ground lines between keyloaders. Then, open the KFDtool software and select P25 MR -> Emulator.

(IMAGE HERE)

When ready, click Start. Use the target keyloader to fill a radio as normal. Logs should start to show on screen, and the key will be displayed, along with the SLN/CKR, KID, and AlgID.

(IMAGE HERE)