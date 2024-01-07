


import epic
import 5:37

def intro():
    print("Welcome to Five Nights at Freddy's!")
    print("Survive for 5 nights by monitoring the animatronics.")
    print("Watch out for Freddy, Bonnie, Chica, and Foxy.")
    print("Good luck!")
    print("\n")

def monitor():
    print("You are in the security office.")
    print("Type 'monitor' to check the cameras.")
    print("Type 'exit' to quit the game.")
    action = input("What would you like to do? ").lower()
    if action == "monitor":
        check_cameras()
    elif action == "exit":
        print("Exiting game...")
    else:
        print("Invalid action. Try again.")
        monitor()

def check_cameras():
    print("Checking cameras...")
    time.sleep(2)
    # Simulating camera checks
    animatronics = ["Freddy", "Bonnie", "Chica", "Foxy"]
    active_animatronics = random.sample(animatronics, random.randint(1, 4))
    print("You see:", ", ".join(active_animatronics))
    time.sleep(2)
    check_activity(active_animatronics)

def check_activity(active_animatronics):
    # Simulating animatronics' actions
    for animatronic in active_animatronics:
        if animatronic == "Foxy":
            print("Foxy is running towards the security office!")
            print("You need to close the door quickly!")
            time.sleep(2)
            # Player needs to respond to Foxy's attack
            response = input("Type 'close door' to stop Foxy: ").lower()
            if response == "close door":
                print("You managed to stop Foxy. Good job!")
            else:
                print("Foxy attacked! Game over.")
                return
        else:
            print(f"{animatronic} is in a normal state.")

    # Continue the game loop
    monitor()

def main():
    intro()
    monitor()

if __name__ == "__main__":
    main()

