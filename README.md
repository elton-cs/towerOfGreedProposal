# TOWER OF GREED
Turn Based Battle Royale built with Paima Engine


## Elevator Pitch

Do you like turn-based rpgs? Do you like action-packed battle royales? Enter, Tower of Greed. A game that fuses the two genres and is powered by DeFi and zero knowledge cryptography. ToG takes skill, precision, luck, and most of all, GREED (in moderation) to win.

## Lore
In the Tower of Greed, 5 dare to enter, and only one makes it out. Players have to fight their way to the top to reach the treasure, the almighty Greediamond. They say that whoever possesses it receives good luck and great fortune, and their names go down in history. Oh and btw, watch out for lava!

## Gameplay Overview

ToG is a 5 player battle royale where each player takes turns to move/attack in the arena, with the objective to climb up the tower while defeating the other players in the process.
Players can lose by either dying to another player, or getting consumed by the chasing lava. The last man standing wins.

Game Flow Chart:
Each game consists of 3 major components: Player Acton, Tower Action, and Round.

1. Player Action: 
- Each player in the game can perform 1 action every round.
- A player action consist of a movement, attack, or both.
  - 1. Movement only: A player can move 3 blocks in any directon
  - 2. Move and attack: A player can move 1 block in any direction and perform 1 attack.
  - 3. Attack only: A player can perform 2 attacks.
- Movement always takes precedence over an attack.

2. Tower Action:
- At the end of every two rounds, the tower can perform an action
  - 1. Feeling Cool (Gracious): The tower creates random spots of healing, when players stay in them or move into them, they get healed for some hp.
    Happens 30% of the time.
  - 2. Feeling Cruel (Gruesome): The edges of the tower get engulfed in lava. If player stay towards the edge of the arena towards 
    the end of round 2, they take 30% of their max hp as damage.
    Happens 70% of the time.

3. Round: Basically one "tick" of the game. All players make their actions during every round. The tower makes its action every 2 rounds. 