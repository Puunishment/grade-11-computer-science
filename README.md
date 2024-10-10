player_alive = True
total_rooms = 10
inventory = {"flashlight": False, "crucifix": False, "vitamin": False, "key1": False}
# Starting
print("When you woke up, you saw yourself in a hotel. In front of you, there is a door with a number of...")
print("1")
choice1 = ""
while choice1 not in ["1", "2"]:
    choice1 = input("[1] Open the first door or [2] Stay in this lobby ")
if choice1 == "1":
    print("You enter door 1, now you are in room 1.")
elif choice1 == "2":
    print("You stayed in the lobby and died of thirst.")
    exit()

print("Nothing in room 1, but door 2 appears.")
choice2 = ""
while choice2 not in ["1", "2"]:
    choice2 = input("[1] Enter door 2 or [2] Keep exploring room 1 for a while ")
if choice2 == "1":
    print("You enter room 2.")
elif choice2 == "2":
    print("You found nothing.")
    print("You enter room 2.")
# Room 2
print("Room 2 is a crossroads. You can see door 3 in front of you.")
at_crossroad = True
while at_crossroad:
    choice3 = ""
    while choice3 not in ["1", "2", "3"]:
        choice3 = input("[1] Turn left, [2] Turn right, [3] Go straight to door 3 ")
    if choice3 == "1":
        print("You found a key! Key1 added to inventory.")
        inventory["key1"] = True
        print("Would you like to go straight to door 3?")
        choice4 = ""
        while choice4 not in ["1", "2"]:
            choice4 = input("[1] Yes or [2] No: ")
        if choice4 == "1":
            print("You enter door 3.")
            at_crossroad = False
        elif choice4 == "2":
            print("You return to the middle of the crossroads.")
    elif choice3 == "2":
        print("You hear a weird voice. Would you like to investigate?")
        choice5 = ""
        while choice5 not in ["1", "2"]:
            choice5 = input("[1] Yes or [2] No: ")
        if choice5 == "1":
            print("OMG, IT'S A CRUCIFIX!")
            print("You return to the crossroads.")
            inventory["crucifix"] = True
        elif choice5 == "2":
            print("You return to the middle of the crossroads.")
    elif choice3 == "3":
        if inventory["key1"]:
            print("The door is locked, but you use the key to unlock it!")
            at_crossroad = False
        else:
            print("The door is locked. You need a key to open it.")
# Room 3
print("You entered room 3.")
print("You saw the lights on the wall flash.")
print("There is a bed and a closet in this room.")
choice6 = ""
while choice6 not in ["1", "2", "3"]:
    choice6 = input("[1] Hide in the closet, [2] Hide under the bed, or [3] Stand still ")
if choice6 == "1":
    print("You saw a black thing rush past, but you survived.")
elif choice6 == "2":
    print("You saw a black thing rush past, but you survived.")
elif choice6 == "3":
    if inventory["crucifix"]:
        print("The crucifix flies out and locks the monster! You survived!")
        inventory["crucifix"] = False
    else:
        print("You were killed by the monster! HINT: Hide when the light flashes.")
        exit()

# Room 4
print("You entered room 4. You hear giggling.")
choice7 = ""
while choice7 not in ["1", "2"]:
    choice7 = input("[1] Look around or [2] Look underneath ")
if choice7 == "1":
    print("You see a head! It screams and disappears. You survived.")
elif choice7 == "2":
    if inventory["crucifix"]:
        print("The crucifix flies out and locks the monster! You survived!")
        inventory["crucifix"] = False
    else:
        print("A head bites you! You are killed! HINT: Look around when you hear giggling.")
        exit()

# Room 5
print("You entered room 5. It's super dark, but you can see door 6.")
choice8 = ""
while choice8 not in ["1", "2"]:
    choice8 = input("[1] Go straight to door 6 or [2] Explore in the darkness ")
if choice8 == "1":
    print("You unlocked door 6.")
elif choice8 == "2":
    print("You see something white.")
    if inventory["crucifix"]:
        print("The crucifix flies out and locks the monster! You survived!")
        inventory["crucifix"] = False
    else:
        print("You were killed by a skeleton! HINT: Do not stay in darkness for too long!")
        exit()

# Room 6
print("You entered room 6. It's eerily silent.")
choice9 = ""
while choice9 not in ["1", "2"]:
    choice9 = input("[1] Investigate a strange noise or [2] Approach a mirror ")
if choice9 == "1":
    print("A trapdoor opens beneath you! You fall to your death.")
    player_alive = False
    exit()
elif choice9 == "2":
    print("The mirror shows your reflection, but it starts moving differently...")
    print("Suddenly, the mirror shatters! You found a hidden passage leading outside. You escape room 6!")
# Room 7
print("You entered room 7, it's dark, and there's a strange smell.")
choice10 = ""
while choice10 not in ["1", "2"]:
    choice10 = input("[1] Light a match to see or [2] Wait for a moment ")
if choice10 == "1":
    print("The room is filled with gas! Lighting the match caused an explosion. You were killed.")
    exit()
elif choice10 == "2":
    print("You wait patiently and find a hidden path leading to safety. You escape the hotel!")
    print("CONGRATULATIONS, YOU Escaped!")
    print("BUT, ACTUALLY??!")

print("TO BE CONTINUED")
print("HAPPY HALLOWEEN")
