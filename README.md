# tic_tac_toe
A two player tic_tac_toe game
This is a two player game , which is built in python
import numpy as np
import sys
class players:
    def __init__(self,name,key):
        self.name = name
        self.key = key
def Board():
    board = np.arange(1,10).reshape(3,3).astype(str)
    return board




class tic_tac_toe:
    def __init__(self,board = None):#here our count of game will act as the instance , so like firstgame , second game they will act as instances
        if board is None:
            self.board = Board()
        else:
            self.board = board


    def __str__(self):
        return self.board

    def displayboard(self):
        print(self.board)

    def replay(self):
        next = input("Replay-->yes/no")
        if(next == "yes"):
                game = tic_tac_toe()
                game.play_game()
        else:
                sys.exit()


    def place_key_atposition(self,p1,position):
        if position in ([1,2,3]):
                self.board[0][position-1] = p1.key
        elif(position in ([4,5,6])):
            self.board[1][position-4] = p1.key
        elif(position in [7,8,9]):
            self.board[2][position-7] = p1.key

    def play_game(self):
        for i in range(5):
            print("player 1 enter your move please\n")
            position = int(input())
            self.place_key_atposition(player1,position)
            self.displayboard()
            self.check_win()

            if(i == 4):
                continue
            else:
                print("player 2 enter your move please\n")
                position = int(input())
                self.place_key_atposition(player2,position)
                self.displayboard()
                self.check_win()
        print("It is a Draw\n")
        self.replay()


    def check_win(self):
        if(self.board[0][0] == self.board[1][0] == self.board[2][0] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[0][1] == self.board[1][1] == self.board[2][1] == 'X'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[0][2] == self.board[1][2] == self.board[2][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[0][0] == self.board[0][1] == self.board[0][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[1][0] == self.board[1][1] == self.board[1][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[2][0] == self.board[2][1] == self.board[2][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[0][0] == self.board[1][1] == self.board[2][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[2][0] == self.board[2][1] == self.board[2][2] == 'X'):
            print("Player 1 WON THE GAME!!!!")
            self.replay()
        elif(self.board[0][0] == self.board[1][0] == self.board[2][0] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[0][1] == self.board[1][1] == self.board[2][1] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[0][2] == self.board[1][2] == self.board[2][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[0][0] == self.board[0][1] == self.board[0][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[1][0] == self.board[1][1] == self.board[1][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[2][0] == self.board[2][1] == self.board[2][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[0][0] == self.board[1][1] == self.board[2][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()
        elif(self.board[2][0] == self.board[1][1] == self.board[0][2] == '0'):
            print("Player 2 WON THE GAME!!!!".center(100,'.'))
            self.replay()



player1 = players("vaibhav yadav","X")
player2 = players("vaibhav gupta","0")
board = Board()
game1 = tic_tac_toe(board)
game1.play_game()

