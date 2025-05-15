# rockpaper-scissor
This Python program is a Rock, Paper, Scissors game where a player competes against the computer. The user selects Rock, Paper, or Scissors, and the computer makes a random choice. The winner is decided based on standard rules. The program displays both choices and the result of each round.




import random
print("Welcome to Rock-Paper-Scissors!")
print("Rules:")
print("- Rock beats Scissors")
print("- Paper beats Rock")
print("- Scissors beats Paper\n")

while True:
    print("Choose one of the following:")
    print("1 - Rock")
    print("2 - Paper")
     print("3 - Scissors")
 
    try:
        user_choice = int(input("Your choice: "))
    except ValueError:
        print("That's not a number. Try again.\n")
        continue

    if user_choice not in [1, 2, 3]:
        print("Invalid choice. Please pick 1, 2, or 3.\n")
        continue

    options = {1: "Rock", 2: "Paper", 3: "Scissors"}
    user_pick = options[user_choice]
    print(f"You chose: {user_pick}")

    comp_choice = random.randint(1, 3)
    comp_pick = options[comp_choice]
    print(f"Computer chose: {comp_pick}")
    if user_pick == comp_pick:
        print("It's a draw!")
    elif (user_pick == "Rock" and comp_pick == "Scissors") or \
         (user_pick == "Paper" and comp_pick == "Rock") or \
         (user_pick == "Scissors" and comp_pick == "Paper"):
        print("You win!")
    else:
        print("Computer wins!")

    again = input("\nPlay again? (y/n): ").strip().lower()
    if again != 'y':
        break
        print("\nThanks for playing!")
        
