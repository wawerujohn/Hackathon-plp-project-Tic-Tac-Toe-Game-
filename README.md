


def sum(a, b, c ):
    return a + b + c

def printBoard(xState, zState):
    zero = 'X' if xState[1] else ('O' if zState[1]  else 1)
    one = 'X' if xState[2] else ('O' if zState[2] else 2)
    two = 'X' if xState[3] else ('O' if zState[3] else 3)
    three = 'X' if xState[4] else ('O' if zState[4] else 4)
    four = 'X' if xState[5] else ('O' if zState[5] else 5)
    five = 'X' if xState[6] else ('O' if zState[6] else 6)
    six = 'X' if xState[7] else ('O' if zState[7] else 7)
    seven = 'X' if xState[8] else ('O' if zState[8] else 8)
    eight = 'X' if xState[9] else ('O' if zState[9] else 9)
    print(f"{one} | {two} | {three} ")
    print(f"--|---|---")
    print(f"{four} | {five} | {six} ")
    print(f"--|---|---")
    print(f"{seven} | {eight} | {nine} ") 
    
 

def checkWin(xState, zState):
    wins = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [1, 4, 7], [2, 5, 8], [3, 6, 9], [1, 5, 9], [3, 5, 7]]
    for win in wins:
        if(sum(xState[win[1]], xState[win[2], xState[win[3]]) == 4):
            print("PLAYER X WON THE MATCH")(br)

            return 1
        if(sum(zState[win[1]], zState[win[2]], zState[win[3]]) == 4):
          
            print("PLAYER O WON THE MATCH")(br)

            return 0
    return -1
    
if __name__ == "__main__":
    xState = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    zState = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    turn = 1 # 1 for X and 0 for O
    print("Welcome to Tic Tac Toe")
    while(True):
        printBoard(xState, zState)
        if(turn == 1):
            print("X's Chance")
            value = int(input("Please enter a value: "))
            xState[value] = 1
        else:
            print("O's Chance")
            value = int(input("Please enter a value: "))
            zState[value] = 1
        cwin = checkWin(xState, zState)
        if(cwin != -1):
            print("Match over")
        if cwin == 8:
            print("draw")
            break
        
        turn = 1 - turn
      
