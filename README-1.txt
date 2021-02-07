READ ME

The following code solves a 9x9 sudoku, with 5 difficulties that are stored in a 15x9x9 array.

To highlight in advance: Unfortunately, my programming skills are limited and I have not managed to successfully solve any puzzles from the "hard" section onwards (hard section included).

This code is composed of 4 functions. My aim has been to follow a backtracking algorithm as covered in the lectures, even though I feel like mine is quite basic still. I chose this algorithm because it is helpful for constraint satisfaction problems like Sudoku puzzles. The agent just backtracks until it finds a valid solution that works. This is particularly implemented in the agent() function.

I chose this design to focus on the 4 main functions (from a logical perspective) that are required as an absolute basic to solve this problem: 1) a sudoku solving function 2) a agent function that deducts the sudoku and returns a sudoku accordingly 3) a function that checks for empty cells and 4) a function that checks the validity of the possible numbers.

To portray the "-1" arrays, I decided to use the numpy.full() function which returns an array of 9x9, filled with -1 as a value. This will then be called throughout the functions. It essentially returns a 2-dimensional array of 9x9. I chose to keep it at the top, along with the sudoku's dictionary of values from 0-9, to  keep the functions less cluttered. 

Please find the functions briefly outlined below.

Sudoku solver: 
Takes input from agent function. The function essentially uses an if statement to return -1s or the valid sudoku puzzle as a result. 

valid_num = I really spent most time on this because I initially used the update() function and was wondering why it was returning an error. But then I noticed that in this function, I want to create and return an entirely new set that contains all of the elements from the set specified. Thats why union() is most appropriate. For update(), it would have updated the set on which the method is called. This website made it clearer for me: https://codedestine.com/python-set-union-example/

agent: 
This function is dedicated to the deduction process of the sudoku.It looks at which cells have a unique solution. If a cell has no possible value, it outputs -1. 

My largest struggle here was that I forgot to include a situation where l=1, which caused me hours of headache after I noticed that it was quite an obvious mistake.

empty_cells: As the name suggests, this function checks the empty cells by checking both rows and columns (a and b)

