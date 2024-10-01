## Project Overview (2 versions: C++, Java)

This project is a 2D virtual world simulator where, both animals and plants, coexist and interact in a simulated environment. The virtual world is a NxM grid where each cell can be occupied by one organism at a time. The organisms are categorized into animals and plants, each behaving according to its specific species. The actions in the simulator are done in turns, and the organisms' actions depend on their initiative and age. Organisms can move, breed, and collide based on their strengths, initiating fights or other interactions. 

The purpose of the game is to survive as a human as long as possible. Human player can move in 4 directions (horizontally, and vertically). Additionally, he can activate a special ability. The simulation is visualized using ASCII symbols in the C++ version, and with an enhanced graphical design in the Java version.

## ORGANISMS
organism is an abstract class for all living entities<br/>
Animal class and Plant class inherits from Organism and implements specific for their kind actions (e.g. moving, spreading, colliding)<br/>
Specific Plants and animals (+ Human) derive from the Animal and Plant class <br/>

### Animals
**Possible actions:**
**- Movement:** Random neighboring field selection.<br/>
**- Collision:** Fights between animals are determined by strength, with species-specific rules.<br/>
**- Breeding:** When two animals of the same species meet, they breed instead of fighting.<br/>

<img width="590" alt="Screenshot 2024-10-01 at 15 05 03" src="https://github.com/user-attachments/assets/0b79dea2-a45c-4ff9-8c04-4261deedf88c">
<img width="592" alt="Screenshot 2024-10-01 at 15 05 19" src="https://github.com/user-attachments/assets/b780e556-06b8-4aff-b068-29e776f222d6">

### Plants
spreading of plant in method action() - with a certain probability the plant can "sow" a new plant on a random free neighboring field.<br/>
<img width="594" alt="Screenshot 2024-10-01 at 15 06 03" src="https://github.com/user-attachments/assets/a93546a9-55d4-477c-a989-8832ca4995a5">



**4. Human Player**
The player controls a human. <br/>
The human has a special ability that can be activated for 5 turns - magical potion: adds 5 to the strength and with each turn it decrements by one until it reaches original strength<br/>
The human’s movement is based on player input, while other animals move randomly.<br/>
<img width="590" alt="Screenshot 2024-10-01 at 15 04 38" src="https://github.com/user-attachments/assets/93d8cd00-6523-46d9-bbcc-171dda68f1f7">

**5. Turn-based Action System**
Each organism performs an action during its turn, starting with the organism with the highest initiative. If two organisms have the same initiative, the older one acts first.<br/>
Collisions between organisms are resolved by comparing their strength values, with species-specific rules applied in some cases (e.g., turtles can reflect weaker attacks, antelopes can escape).

**6. User Interface**
In the C++ version, the virtual world is visualized in a console window using characters from keyboard to represent organisms.<br/>
The Java version introduces a fully designed graphical interface using Swing, providing a more interactive experience.

**Implementations in Java**
**New Feature:** Users can add new organisms to the grid by clicking on a particular cell, choosing from a list of available organisms to place.
**Cyber-sheep:** A special animal type introduced in the Java version, which specifically targets and eliminates Sosnowsky's hogweed. When there are no hogweeds present, the cyber-sheep behaves like a regular sheep.

**Saving/Loading:** The current state of the world can be saved to a file and loaded later (available in both C++ and Java versions).
