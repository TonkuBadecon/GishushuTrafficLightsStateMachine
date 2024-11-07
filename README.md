# Gishushu Traffic Lights State Machine
=====================================

Overview:
---------
The Gishushu Traffic Lights State Machine controls traffic flow at a four-way intersection with traffic lights in four directions: West, North, East, and South. Each direction has green, yellow, and red light states, which activate in sequence to allow vehicles from one direction to proceed while all others remain stopped. The system cycles through these lights in a fixed order, with each green phase followed by a yellow warning before turning red.

Initial State:
--------------
1. All Directions Red - At system startup, all lights remain red.
2. Transition to North Green - When the initial timer expires, North green light is activated, allowing northbound traffic to proceed while all other directions remain red.

State Sequences:
----------------

1. North Direction Sequence:
   - North Green, Others Red - Northbound traffic proceeds. 
     - Transition: After the green duration expires, the light changes to yellow.
   - North Yellow, Others Red - Northbound traffic light turns yellow.
     - Transition: After the yellow duration expires, the light turns red, and East Green activates.

2. East Direction Sequence:
   - East Green, Others Red - Eastbound traffic proceeds.
     - Transition: After the green duration expires, the light changes to yellow.
   - East Yellow, Others Red - Eastbound traffic light turns yellow.
     - Transition: After the yellow duration expires, the light turns red, and South Green activates.

3. South Direction Sequence:
   - South Green, Others Red - Southbound traffic proceeds.
     - Transition: After the green duration expires, the light changes to yellow.
   - South Yellow, Others Red - Southbound traffic light turns yellow.
     - Transition: After the yellow duration expires, the light turns red, and West Green activates.

4. West Direction Sequence:
   - West Green, Others Red - Westbound traffic proceeds.
     - Transition: After the green duration expires, the light changes to yellow.
   - West Yellow, Others Red - Westbound traffic light turns yellow.
     - Transition: After the yellow duration expires, the light turns red, and All Directions Red briefly activates before the cycle restarts with North Green.

Cycle Restart:
--------------
- All Directions Red - After each full cycle (West -> North), all directions remain red for a brief period before restarting with North Green.


