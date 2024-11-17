import random
import time

def print_with_pause(message):
    """Prints a message with a short delay for dramatic effect."""
    print(message)
    time.sleep(2)

def start_game():
    """Starts the horror cave escape game."""
    print_with_pause("You wake up in a dark, damp cave.")
    print_with_pause("The sound of dripping water echoes all around.")
    print_with_pause("You feel a chill run down your spine as you realize you're not alone...")
    first_choice()

def first_choice():
    """Handles the player's first decision."""
    print_with_pause("\nWhat will you do?")
    print("1. Look around for an exit.")
    print("2. Stay still and listen.")
    choice = input("Enter your choice (1 or 2): ")
    
    if choice == "1":
        explore_cave()
    elif choice == "2":
        encounter_creature()
    else:
        print_with_pause("Invalid choice. Try again.")
        first_choice()

def explore_cave():
    """Player chooses to explore the cave."""
    print_with_pause("\nYou cautiously move through the cave, feeling the walls for guidance.")
    print_with_pause("You hear distant growls. Something is hunting you.")
    print("1. Hide behind a rock.")
    print("2. Run towards the sound of water.")
    choice = input("Enter your choice (1 or 2): ")

    if choice == "1":
        print_with_pause("\nYou crouch behind a rock, trying to stay quiet.")
        if random.choice([True, False]):
            print_with_pause("The creature sniffs the air but passes by without noticing you.")
            print_with_pause("You take the opportunity to move further into the cave.")
            escape_path()
        else:
            print_with_pause("The creature finds you and you meet a gruesome end...")
            play_again()
    elif choice == "2":
        print_with_pause("\nYou sprint towards the sound of water, hoping for an exit.")
        print_with_pause("The ground beneath you gives way, and you fall into an underground river!")
        river_escape()
    else:
        print_with_pause("Invalid choice. Try again.")
        explore_cave()

def encounter_creature():
    """Player chooses to stay still and listen."""
    print_with_pause("\nYou hold your breath and listen carefully.")
    print_with_pause("The growling gets louder... closer.")
    if random.choice([True, False]):
        print_with_pause("The creature passes by without noticing you.")
        print_with_pause("You quietly get up and start looking for an exit.")
        explore_cave()
    else:
        print_with_pause("The creature lunges at you from the shadows!")
        print_with_pause("You were too slow to react. Game over.")
        play_again()

def river_escape():
    """Player falls into a river and must make a choice."""
    print_with_pause("\nYou are swept away by the river's current!")
    print_with_pause("You see light ahead. It might be an exit.")
    print("1. Swim towards the light.")
    print("2. Try to grab onto the cave wall.")
    choice = input("Enter your choice (1 or 2): ")

    if choice == "1":
        print_with_pause("\nYou swim with all your strength towards the light.")
        print_with_pause("You emerge from the cave into the sunlight!")
        print_with_pause("You have escaped the horror cave. Congratulations!")
        play_again()
    elif choice == "2":
        print_with_pause("\nYou grab onto the slippery cave wall.")
        print_with_pause("The current is too strong, and you are pulled under...")
        print_with_pause("You lose consciousness and never wake up. Game over.")
        play_again()
    else:
        print_with_pause("Invalid choice. Try again.")
        river_escape()

def escape_path():
    """Player finds an escape path in the cave."""
    print_with_pause("\nYou find a narrow tunnel that might lead outside.")
    print_with_pause("The growls are getting louder. You must act fast.")
    print("1. Crawl through the tunnel.")
    print("2. Stay and fight the creature.")
    choice = input("Enter your choice (1 or 2): ")

    if choice == "1":
        print_with_pause("\nYou crawl through the tunnel, scraping your arms and knees.")
        print_with_pause("The tunnel opens up, and you see daylight ahead!")
        print_with_pause("You have escaped the horror cave. Congratulations!")
        play_again()
    elif choice == "2":
        print_with_pause("\nYou pick up a sharp rock and prepare to fight.")
        if random.choice([True, False]):
            print_with_pause("You manage to scare the creature away!")
            print_with_pause("You use this chance to find the exit and escape. Congratulations!")
        else:
            print_with_pause("The creature overpowers you. You meet a gruesome end.")
        play_again()
    else:
        print_with_pause("Invalid choice. Try again.")
        escape_path()

def play_again():
    """Asks the player if they want to play again."""
    print("\nWould you like to play again? (yes or no)")
    choice = input().lower()

    if choice == "yes":
        start_game()
    elif choice == "no":
        print_with_pause("\nThank you for playing! Goodbye!")
    else:
        print_with_pause("Invalid choice. Try again.")
        play_again()

# Start the game
start_game()
