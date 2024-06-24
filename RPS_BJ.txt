from random import randint 
import time
import os

    ### fairly simple code game for rock paper scissors
def clear_screen():
    
    os.system('cls' if os.name == 'nt' else 'clear')
    ### defines how/when it clears the screen



def main():
    OPTIONS = ["ROCK", "PAPER", "SCISSORS"]
    PC = OPTIONS[randint(0,2)]
    #### random integer to represent rock paper or scissors

    player1 = False
    ### set to false in order to prompt user until an appropriate entry is made
    while player1 == False:
        player1 = input('ROCK, PAPER, OR SCISSORS?').upper()
        if player1 == PC:
            print("TIE!")
        elif player1 == "ROCK":
            if PC == "PAPER":
                print("HA YOU LOSE!", PC, "covers", player1)
            else:
                print("DARN, YOU GOT ME!", player1, "smashes", PC)
        elif player1 == "PAPER":
            if PC == "SCISSORS":
                print("HA LOSER! I WIN!", PC, "cut", player1)
            else:
                print("WHAT? YOU WON? YOU MUST'VE CHEATED!", player1, "covers", PC)
        elif player1 == "SCISSORS":
            if PC == "ROCK":
                print("YOU LOSE. TRY AGAIN NEXT YEAR BUD!", PC, "smashes", player1)
            else:
                print("YOU WIN! OKAY I SEE YOU!", player1, "cut", PC)
        else:
            print("Check your entry!")
            player1 = False  
    #### the above dialogue describes the possibilities of combinations between user and PC
    ### as well as the possible outcomes.

    runitback = input("Do you want to run it back? ENTER YES/NO : ").upper()
    if runitback == 'YES':
        print("LOL back for more? OK let's go!")
        main()
    elif runitback == 'NO':
        print("Hold that L. Later buddy!")
        print('logging out...')
        time.sleep(5)  
        clear_screen()
    ### restarts the program, from the beginning prompt. 
    ## if chosen not to proceed, it will close out with a time delay of 5 seconds.
main ()