<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works


Players select villagers using a 3-bit DIP switch (I0–I2) and perform actions with I3 (Investigation), I4 (Accusation), and I5 (Advance Night). Combinational gates (AND, OR, NOT, XOR) decode the villager selection, determine wolf identity, and calculate game outcomes. Sequential logic using D flip-flops implements a 2-bit night counter, updating the game state over time. LEDs indicate suspicion (orange), death (red), win (green), and wolf detected

## How to test

Set the inputs using the DIP switches and observe the LEDs for expected behavior:

| Villager Selected | Investigation (I3) | Accusation (I4) | Night Advance (I5) | Expected LEDs |
|------------------|------------------|----------------|-------------------|---------------|
| Villager 0       | 1                | 0              | 0                 | Wolf detected if wolf, otherwise nothing |
| Villager 1       | 0                | 1              | 0                 | Win if correct accusation, Death if wrong |
| Any              | 0                | 0              | 1                 | Night counter advances (flip-flops update) |

Press I5 to advance the night and ensure the flip-flops update sequentially. Verify that the LED outputs correctly reflect suspicion, correct/incorrect accusations, and wolf detection according to the game logic. 

## External hardware

LEDs
