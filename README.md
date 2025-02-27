# Breadboard Vending Machine
Breadboard Vending Machine/SR Latch documentation for CRT 205: Physical Computing.

# What is SR Latch?
Set-Reset Latch (SR Latch) is a device that uses the binary system where 0 is false and 1 is true. It uses digits S (set) and R (reset) to indicate inputs and these values can be represented by 0 or 1. Depending on the sum of the combinations, the output (Q) will be different. Unlike other circuits that are simple on/off switches, Q is an output that remembers the sum of the inputs.

An additional output called NOT Q is represented by Q with a line over it. Essentially, it is the opposite of the Q value. If Q is 1, NOT Q is 0, and vice versa. This value will be explained further in the README file.

![image](https://github.com/user-attachments/assets/bba6afc2-296f-4da7-9bba-6d7494af939c) - NOT Q symbol

# Truth Table
![image](https://github.com/user-attachments/assets/35715a56-3a30-4ca8-9342-057e291b213f)
1. When S and R are set to 0 the output holds the previous value inputted into the circuit.
2. When S is set to 0 and R is set to 1, the output resets. The circuit will forget any stored information.
3. When S is set to 1 and R is set to 0, this starts the circuit at the beginning.
4. When S and R are set to 1, the output will be invalid because you cannot simultaneously set and reset a circuit. One action must be performed before the other. The output (Q) will be set as undefined.

# Electronics Diagram
1. Here is the electronics diagram for the SR Latch mechanism. This is the diagram without any inputs or outputs to represent the wiring needed to construct one. Reference the truth table above to see the operations.

![image](https://github.com/user-attachments/assets/4cd79345-a8d2-4f81-9f68-6e5dd0e08a5e)

2. In this figure, since R is 1 and S is 0, the output of Q is 0. Since NOT Q is the opposite of the Q value, not Q is 1.

![image](https://github.com/user-attachments/assets/de7a5a45-6182-41f0-8908-b99fc7fbf510)

3. In this figure, S and R are both 0, indicating a reset, and the output of Q is 0. Since NOT Q is the opposite of the Q value, not Q is 1.
![image](https://github.com/user-attachments/assets/c0bb5cee-b0ff-4558-9a16-37606e2637e6)

4. In this figure, S is 1 and R is 0, indicating a set or initialization. Since the output (Q) is 1, the NOT Q value is 0.

![image](https://github.com/user-attachments/assets/ef127a15-b315-4dec-845e-b755e630d998)

5. If we use the representation above, the output (Q) has now held the set value of 1. Setting S and R to 0 in this diagram shows that the output (Q) is stored in the circuit as 1. NOT Q is zero because it is the opposite of 1.

![image](https://github.com/user-attachments/assets/23e5e1aa-cdb3-4643-8bd4-dd97dcb2107a)

Operations 4 & 5 represent a user slotting a coin into a vending machine (when done sequentially). For a vending machine purchase to work, the user must insert a coin into the machine, and the machine must recognize/remember that a coin has been inserted into the machine.

# The Circuit Types
## Circuit 1: The Manual Circuit

![image](https://github.com/user-attachments/assets/76261c3f-e942-4eca-bfa9-7c96b400c132)

Designed for ease of use, this circuit includes set/reset modules and coin/vend LED displays. This design is simple for any operational switches, such as buttons, slide switches, and wired buttons. The only caveat is that every operation must be manually operated. 

## Circuit 2: The Coin Focused Circuit
![image](https://github.com/user-attachments/assets/c1c164f4-b11c-41ff-9189-37c69a577dc0)

This design features a reset that focuses on the coin. Essentially, the coin will be stuck until the user purchases an item. This method is not preferred since the user's money is stuck in the machine until a purchase is made. 

## Circuit 3: The Delayed Reset Circuit - Conceptually Flawed Design
![image](https://github.com/user-attachments/assets/2cb1e12e-cf18-4fe8-aca5-607d8a62eddd)

Conceptually, this delayed reset circuit should work. However, the only issue is that the delayed reset occurs too quickly. Instead, the goal should be to instate a delay after the VEND LED produces a signal. 

# Delayed Reset Circuit
A delayed reset circuit is a capacitor that utilizes a 4.7KΩ resistor, a 200µF electrolytic capacitor, and extra wires. It charges up for a set amount of time until the machine can be reset. This process can be represented by a vending machine dispensing an item after purchase. After the item falls into the vending well, the machine resets, and another coin must be inserted to restart the process. More technical parts of the vending machine require sensors to tell if an item has been fully dispensed.


# The Visual
## Step 1: The Layout/Reset
![step11](https://github.com/user-attachments/assets/cc3878a1-496d-46cc-b862-05fc8419eebd)

This image shows the layout and labels of the important components of the vending machine.

## Step 2: Set
![step22](https://github.com/user-attachments/assets/c31460c7-408b-4633-9930-f663724b40a2)

In this image, pressing the coin button sets the machine. The machine remembers that the coin is in.

## Step 3: Vend
![step33](https://github.com/user-attachments/assets/202cfa8b-aa55-481f-9364-7a039ba9520e)

When both lights are on, the machine remembers that the coin is in, and the machine vends an item to the buyer. The added delayed reset gives the machine time to reset after the machine dispenses an item.


# Classic Vending Machine
![image](https://github.com/user-attachments/assets/78219630-a38a-4adc-9ac3-fe9e1304adc5)

The SR Latch vending machine is a simplified version of a classic vending machine. 


# Citations
Justice, M. (2021). How computers really work: A hands-on guide to the inner workings of the Machine. No Starch Press, Inc.

Ryoko. (2019, September 16). Upgrading the Tinkering Vending Machine!. Exploratorium. https://www.exploratorium.edu/tinkering/blogs/upgrading-tinkering-vending-machine 

Urias, O. M. (2023, February 21). The S-R latch (quickstart tutorial). Build Electronic Circuits. https://www.build-electronic-circuits.com/s-r-latch/ 

# Additional Resources
Bigelow, S. J. (2023, June 7). What is a Microfarad?: Definition from TechTarget. WhatIs. https://www.techtarget.com/whatis/definition/microfarad 

Budgetronics. (n.d.). Home. explained. https://www.budgetronics.eu/en/capacitor-codes/c-15 

Mistablik. (2018, January 2). The Soda Locker - Vending Machine. Instructables. https://www.instructables.com/The-Soda-Locker-Vending-Machine/ 

Sheldon, R. (2023, January 18). What is an Ohm and what does it measure? – TechTarget definition. WhatIs. https://www.techtarget.com/whatis/definition/ohm 

