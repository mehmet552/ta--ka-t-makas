import random

def taş_kağıt_makas_MehmetSiyarsalman():
    print("Welcome to the Rock, Paper, Scissors game!")
    print("Rules: Rock beats Scissors, Scissors beats Paper, Paper beats Rock.")
    print("Press 'q' to exit the game.")

    options = ["rock", "paper", "scissors"]

    while True:
        player_wins = 0
        computer_wins = 0

        while player_wins < 2 and computer_wins < 2:
            player_choice = input("Make your choice (rock, paper, scissors): ").lower()
            if player_choice == 'q':
                print("You exited the game.")
                return
            if player_choice not in options:
                print("Invalid choice, please try again.")
                continue

            computer_choice = random.choice(options)
            print(f"Computer's choice: {computer_choice}")

            if player_choice == computer_choice:
                print("It's a tie!")
            elif (player_choice == "rock" and computer_choice == "scissors") or \
                 (player_choice == "scissors" and computer_choice == "paper") or \
                 (player_choice == "paper" and computer_choice == "rock"):
                print("Player wins!")
                player_wins += 1
            else:
                print("Computer wins!")
                computer_wins += 1

            print(f"Score: Player {player_wins} - {computer_wins} Computer")

        if player_wins == 2:
            print("You won the game!")
        else:
            print("Computer won the game!")

        continue_game = input("Do you want to play another game? (y/n): ").lower()
        if continue_game == 'y':
            computer_continue = random.choice(['y', 'n'])
            if computer_continue == 'y':
                print("Computer also wants to play a new game. Starting a new game!")
            else:
                print("Computer doesn't want to play a new game. The game is over.")
                break
        else:
            print("The game is over.")
            break

taş_kağıt_makas_MehmetSiyarsalman()
