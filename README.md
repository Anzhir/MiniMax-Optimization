## Game Theory & TicTacToe

# Description
- Minimax agent to play tictactoe.
- Transposition Table optimization to scale up to larger games.
- Minimax To generate Data about the game and then train a neural network to play efficiently and to generalize.

https://user-images.githubusercontent.com/64399795/176794119-b0aa8af7-7053-4697-9058-c1ab31b750b4.mp4

# Minimax 
in a games where there's 2 players a player who is trying to maximize his rewards and another to minimize player1's reward
you can build up the game tree assuming that the other player will play optimally and try to win or minimize other player's reward

![400px-Minimax svg](https://user-images.githubusercontent.com/64399795/176794989-aec2c947-cc7c-42cc-9073-2b163e491177.png)

# Transposition Table
A transposition table is a cache of previously seen positions, and associated evaluations, in a game tree generated by a computer game playing program. If a position recurs via a different sequence of moves, the value of the position is retrieved from the table, avoiding re-searching the game tree below that position. Transposition tables are primarily useful in perfect-information games (where the entire state of the game is known to all players at all times). The usage of transposition tables is essentially memoization applied to the tree search and is a form of dynamic programming.

Transposition tables are typically implemented as hash tables encoding the current board position as the hash index. The number of possible positions that may occur in a game tree is an exponential function of depth of search, and can be thousands to millions or even much greater. Transposition tables may therefore consume most of available system memory and are usually most of the memory footprint of game playing programs.

# My implementation

i made a script that everytime you play and minimax is run it saves all the tree in a database and then minimax is modified to be as follow , search the db first if it's there return the value of the move , else run minimax
The database is kept , but if we were to do a hash table it would rebuild everytime

![transposition](https://user-images.githubusercontent.com/64399795/176795108-b7af4490-95c9-4a02-8120-ef84c0a185c8.png)
![image](https://user-images.githubusercontent.com/64399795/176797340-5f0da284-f6a8-44c8-9375-7436a592a517.png)

# Use the data to train a network

The collected data in the database is then stored as a csv and then used in a python script to train the network 

# Results

![Accuracy](https://user-images.githubusercontent.com/64399795/176797618-b5cd82f0-3405-49fd-a3bb-8e6182e0f6cb.png)
![Loss](https://user-images.githubusercontent.com/64399795/176797622-cee046f9-5ba9-4d8e-b539-951b6e3cb5b8.png)
![training](https://user-images.githubusercontent.com/64399795/176797635-695d0b8f-f2dd-45ba-8604-bbc5ebc26e4c.png)
![Test](https://user-images.githubusercontent.com/64399795/176797639-31464b0c-9413-4083-af91-a23fd713bd66.png)
