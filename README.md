# Algorithms and Data Structures(ADS) - 2019-2020
## Barbu Angelo-Gabriel - angelo.barbu123@gmail.com

### Description:
During the International ATP Cup Tournament, each participating country has a team of players. This team will represent their country in a series of matches played against the members of the other teams. It is desired to create a software solution that will automate the tournament.
The solution simulates the tennis tournament and automates it, respecting the given tasks.

### Tasks:
1. A circular doubly linked list with sentinel, will be created, in which the countries will be added at the end of the list.

2. From the list generated in the previous requirement, countries will be eliminated until their total number is the maximum value of power of 2 possible by the following criteria: the lowest initial score of the country, being the arithmetic average of the players that represent the country.

3. The following data structures will be implemented and the following procedures will be performed on them for the good progress of the tournament:
- A stack will be created in which all the countries remaining in the tournament will be added, starting from the sentinel.
- Two countries will be removed from the stack, successively, between which the matches will be played. The procedure is repeated until the stack is empty.
- For each pair of countries extracted from the stack, a queue will be created in which the matches between the players will be stored.
- Each player in the lot of the first country will play with each player in the lot of the second country, in the following order: the first player in the lot of the first country confronts, in turn, with all the players in the second lot, the second player in the lot of the first country with all the players in the second, etc.
- The player with the higher personal score wins. He is added 5 points to his personal score, and the country for which he plays receives 3 points to the local score. If the two players have equal personal scores, it is considered a draw. Each player is added 2 points to his personal score, and each country receives 1 point to the local score.
- The queue of matches between two countries has been emptied. The confrontation between the two is over. The local scores of the two countries will be checked. The two countries will add the local score, accumulated during the matches between the players, to the global score, but only the country with the higher local score will win.
- In case of a draw, the country in whose lot the player with the highest personal score (between the personal scores of the players of the two countries) is considered the winner. If there is a tie between the two personal scores of the two best players, the first country to be removed from the stack is declared the winner.
- A WINNER stack will be created, in which the winning countries will be added after the matches.
- When the initial stack becomes empty, this stage of the tournament can be considered over. The countries will be removed from the WINNER stack and added in turn to the initial stack. The previous procedures will be repeated for each stage of the tournament, in other words until only one winning country remains in the WINNER stack.

4. A BST - binary search tree will be created, in which the players of the last 4 countries remaining in the tournament will be found, depending on the personal score obtained from the end of the last stage of the tournament.
If one of the players has the same personal score as one already existing in the tree, the player whose name is smaller lexicographically will be added. (The last name is compared first, in case of equality the first name of the players will be compared.)

5. In the cerinte.in file, as presented above, the name and surname of 2 players will be found. The number of players between them in the BST is required (the 2 players are not included). More explicitly, the number of players who have the personal score included between the two personal scores is requested.

### Solution:
The solution has the following files:
- main.c
- functions.c, containing the functions that solve the tasks
- header.h, containing the structures and the function prototypes
- Makefile, containing the build and clean targets

The functions.c contains the following functions:

- fileOpenCheck, checks if the file was opened correctly

- doubleAllocCheck, listAllocCheck, charAllocCheck, etc are functions that check if the memory was allocated correctly

- Read is a function that reads the input file and stores the data in the doubly circular linked list with sentinel

- WriteCountry prints the name of the countries from the list

- Write checks the information stored in the list

- deleteNode, pushStack, popStack, createQueue, enQueue, deQueu are functions that implement the operations on the stack and queue

- Power is a function that computes the number of countries that will remain in the list

- deleteCountry is a function that deletes the countries with the lowest score until the number of countries is equal to the value returned by Power

- Task3 is a function that solves the third task

- newBSTnode, insertBST, printBST(Right-Root-Left) are functions that implement the operations on the binary search tree

- Task4 is a function that solves the fourth task

- checkBST is a function that checks if the two players from the input file are in the binary search tree

- countBST is a function that counts the players whose score is between the scores of the two players from the input file

- Task5 is a function that solves the fifth task

- freeList, freeBST are functions that free the memory allocated for the list and the binary search tree

The main.c contains the main function, that has as parameters the names of the input and output files



### Checker
Autor Checker: Eduard-Claudiu Ciurezu

CHECKER-ul contine 15 teste:
"data" contine input-ul testelor
"ref" contine output-ul corect cu care este comparat output-ul programului
"checker.sh" este script-ul shell ce constituie checker-ul efectiv. Pentru rularea corecta, este necesara comanda "make".
Se ruleaza checker.sh, iar obtinerea rezultatului 135p/135p valideaza corectitudinea si eficienta programului.

Checker author: Eduard-Claudiu Ciurezu

The checker contains 15 tests:
- "data" contains the input of the tests
- "ref" contains the correct output with which the program output is compared
- "checker.sh" is the shell script that constitutes the actual checker. For correct running, the "make" command is required.
- Run checker.sh, and obtaining the result 135p / 135p validates the correctness and efficiency of the program.



