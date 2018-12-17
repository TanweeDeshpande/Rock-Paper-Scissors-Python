# Rock-Paper-Scissors-Python

# The key idea of this program is to equate the strings
# "rock", "paper", "scissors", to numbers
# as follows:
#
# 0 - rock
# 1 - paper
# 2 - scissors


import random

def name_to_num(name):
    '''
    (str)->int

    Returns coorespopnding number for entered name.

    >>> name_to_num('rock')
    0
    >>> name_to_num('paper')
    1
    >>> name_to_num('scissors')
    2
    >>> name_to_num('bleh')
    'Invalid name.'
    '''

    if(name.lower() == 'rock'):
        return 0
    elif(name.lower() == 'paper'):
        return 1
    elif(name.lower() == 'scissors'):
        return 2
    else:
        print("Invalid name.")
        raise SystemExit(4)   #to terminate prog


def num_to_name(num):
    '''
    (int)->str

    Returns coorespopnding name for entered number.

    >>> num_to_name(0)
    rock
    >>> num_to_name(1)
    paper
    >>> num_to_name(2)
    scissors
    '''

    if(num == 0):
        return 'rock'
    elif(num == 1):
        return 'paper'
    elif(num == 2):
        return 'scissors'


def play():
    #accept and display user choice
    player_choice = input("Enter player's choice: ")

    #get user's choice's number
    player_num = name_to_num(player_choice)

    #get comp to generate random number
    comp_num = random.randrange(0,3)

    #get comp's number's corresponding choice
    comp_choice = num_to_name(comp_num)

    #display comp choice
    print("Computer chooses " + comp_choice)

    #compute winner
    if(((comp_num + 1)%3) == player_num):
        print("Player wins!")
    elif(comp_num == player_num):
        print("It's a tie!")
    else:
        print("Computer wins!")


def main():
    ans = input("Press 1 to start: ")
    while(ans == '1'):
        play()
        ans = input("Press 1 to continue: ")


if __name__ == "__main__":
    main()
