# Python-course
# Tic Tac Toe project
####################################################################################################################################
## A function that can print out a board. Set up your board as a list, where each index 1-9 corresponds with a number on a number pad, so you get a 3 by 3 board representation.

from IPython.display import clear_output
def display_board(board):
    print("        |       |       \n    {}   |   {}   |    {}  \n________|_______|_______".format(board[7],board[8],board[9]))
    print("        |       |       \n    {}   |   {}   |    {}  \n________|_______|_______".format(board[4],board[5],board[6]))
    print("        |       |       \n    {}   |   {}   |    {}  \n        |       |       ".format(board[1],board[2],board[3]))

board = [' ',' ',' ',' ',' ',' ',' ',' ',' ',' ']
display_board(board)
####################################################################################################################################
## a function that can take in a player input and assign their marker as 'X' or 'O'. Think about using while loops to continually ask until you get a correct answer.

def player_input():
    while True:
        marker = input("Press x to choose x or o to choose o:\n")
        if marker == 'x' :
            print("Player1 have choosen:  "+marker)
            return marker
        elif marker == 'o':
            print("Player1 have choosen:  "+marker)
            return marker
        else:
            print("wrong input")
####################################################################################################################################  
## a function that takes in the board list object, a marker ('X' or 'O'), and a desired position (number 1-9) and assigns it to the board.

def place_marker(board, marker, position):
    while True:
        if position in [1,2,3,4,5,6,7,8,9]:
            board[position] = marker
            display_board(board)
            break
        else:
            print("Invalid input position!")
            position = int(input ("Type down the position you want to take:"))
####################################################################################################################################
## a function that takes in a board and a mark (X or O) and then checks to see if that mark has won.

def win_check(board, mark):
    if board[1] == board [2] == board[3] == mark:
        return True
    elif board[4] == board[5] == board[6] == mark:
        return True
    elif board[7] == board[8] == board[9] == mark:
        return True
    elif board[1] == board[4] == board[7] == mark:
        return True
    elif board[2] == board[5] == board[8] == mark:
        return True
    elif board[3] == board[6] == board[9] == mark:
        return True
    elif board[1] == board[5] == board[9] == mark:
        return True
    elif board[7] == board[5] == board[3] == mark:
        return True
    else:
        return False
####################################################################################################################################    
## a function that uses the random module to randomly decide which player goes first.

import random

def choose_first():
    n = random.randint(1,2)
    if n == 1:
        print ("Player 'x' goes first")
        return 'x'
    else:
        print ("Player 'o' goes first")
        return 'o'
####################################################################################################################################
## a function that returns a boolean indicating whether a space on the board is freely available

def space_check(board, position):
    return board[position] == ' ' 
####################################################################################################################################
## a function that checks if the board is full and returns a boolean value. True if full, False otherwise.
def full_board_check(board):
    if ' ' in board:
        return False
    else:
        return True
####################################################################################################################################     
## a function that asks for a player's next position (as a number 1-9) and then uses the function from step 6 to check if it's a free position. If it is, then return the position for later use

def player_choice(board):
    position = input("Type down your next position:")
    if space_check(board,position) == True:
        return position
    else:
        return False
####################################################################################################################################
## a function that asks the player if they want to play again and returns a boolean True if they do want to play again

def replay():
    while True:
        i = input("Play again?(y/n)")
        if i == 'y':
            return True
        elif i == 'n':
            return False
        else:
            print("Invalid input") 
####################################################################################################################################
## A function that clears the board.

def clear_board(board):
    board = [' ',' ',' ',' ',' ',' ',' ',' ',' ',' ']
    return board  
