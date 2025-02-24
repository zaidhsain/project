import random

def get_computer_choice():
    return random.choice(["pierre", "papier", "ciseaux"])

def determine_winner(user, computer):
    if user == computer:
        return "Égalité !"
    elif (user == "pierre" and computer == "ciseaux") or \
         (user == "papier" and computer == "pierre") or \
         (user == "ciseaux" and computer == "papier"):
        return "Vous gagnez !"
    else:
        return "L'ordinateur gagne !"

def main():
    while True:
        user_choice = input("Choisissez pierre, papier ou ciseaux (ou 'quit' pour arrêter) : ").lower()
        if user_choice == "quit":
            break
        if user_choice not in ["pierre", "papier", "ciseaux"]:
            print("Choix invalide. Essayez encore.")
            continue
        
        computer_choice = get_computer_choice()
        print(f"L'ordinateur a choisi : {computer_choice}")
        print(determine_winner(user_choice, computer_choice))

if __name__ == "__main__":
    main()
