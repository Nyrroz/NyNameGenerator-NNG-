"""
*********************************-NyNameGenerator(or NNG) created by Nyrroz-***************************************
- Version: 1.00 (Only version)

- Description:
--> This tool allows you to randomly mix or reverse your input(string).

- Credits:
--> Created by Nyrroz
--> github: https://github.com/Nyrroz

"""


import string, random, time
import keyboard

"""
COMING SOON...

def consonants():
    alphabet = string.ascii_lowercase
    consonnants = []
    vowels = []
    for i in range(len(alphabet)):
        if alphabet[i] == 'a':
            vowels.append(alphabet[i])
        if alphabet[i] == 'e':
            vowels.append(alphabet[i])
        if alphabet[i] == 'i':
            vowels.append(alphabet[i])
        if alphabet[i] == 'o':
            vowels.append(alphabet[i])
        if alphabet[i] == 'u':
            vowels.append(alphabet[i])
        if alphabet[i] == 'y':
            vowels.append(alphabet[i])
        else:
            consonnants.append(alphabet[i])
    consonnants.remove(vowels[0])
    consonnants.remove(vowels[1])
    consonnants.remove(vowels[2])
    consonnants.remove(vowels[3])
    consonnants.remove(vowels[4])

    return consonnants

def vowels():
    alphabet = string.ascii_lowercase
    consonnants = []
    vowels = []
    for i in range(len(alphabet)):
        if alphabet[i] == 'a':
            vowels.append(alphabet[i])
        if alphabet[i] == 'e':
            vowels.append(alphabet[i])
        if alphabet[i] == 'i':
            vowels.append(alphabet[i])
        if alphabet[i] == 'o':
            vowels.append(alphabet[i])
        if alphabet[i] == 'u':
            vowels.append(alphabet[i])
        if alphabet[i] == 'y':
            vowels.append(alphabet[i])
        else:
            consonnants.append(alphabet[i])
    consonnants.remove(vowels[0])
    consonnants.remove(vowels[1])
    consonnants.remove(vowels[2])
    consonnants.remove(vowels[3])
    consonnants.remove(vowels[4])

    return vowels

#feature coming soon...
def mix(name):
    name = str(name)
    mixed = ""


    mixed += name[0]


    for i in range(1, len(name)):

        if name[i] in cons:
            print("con detected!")

        else:
            print("vow detected!")
"""


def reverse_mix(input):

    input_len = len(input)
    reversed_str = ""

    for index in range(input_len):
        reversed_str += input[(input_len - 1) - index]

    return reversed_str


def rand_mix(name):

    mixed = ""

    for i in range(len(name)):
        rand_index = random.randrange(len(name))
        mixed += name[rand_index]

    return mixed


def reversed_rand_mix(name):
    name = reverse_mix(name)

    mixed = ""

    for i in range(len(name)):
        rand_index = random.randrange(len(name))
        mixed += name[rand_index]

    return mixed


def credit():
    print("**NyNameGenerator (NNG) tool created by Nyrroz**")
    print("Github: https://github.com/Nyrroz")
    print("Version: 1.00\n")

def controls():
    print("\n")
    print("Controls: ")
    print("- Use 'g' for a generation/regeneration (GENERATE)\n"
          "- Use 'c' for a custom amount of generations (NUMBER)\n"
          "- Use 'r' to set a something to generate from (STRING)\n"
          "- Use 'h' for help (HELP)\n"
          "- Use 'm' to see the credits (CREDITS)\n"
          "- Use 's' to shut down the program (QUIT)")
    try:
        print("\n")
    except:
        pass

delay = 0.3
delay_shutdown = 0.5

name = ""
credit()
controls()

while True:

    if keyboard.is_pressed('g'):
        time.sleep(delay)
        if name == "":
            name = input("Enter something to generate the name from: ")
            print("Use 'g' to genenerate")
        else:
            print("\n")
            print("Reversed: " + reverse_mix(name))
            print("Randomly mixed: " + rand_mix(name))
            print("Reversed & Randomly Mixed: " + reversed_rand_mix(name))
            print("\n************Success!***************")
            print("Use 'h' to see the controls\n")
    if keyboard.is_pressed('r'):
        time.sleep(delay)
        name = input("Enter something to generate the name from: ")
        print("Use 'g' to genenerate")
        print("\n")
    if keyboard.is_pressed('s'):
        time.sleep(delay)
        print("Shutting down the program...")
        time.sleep(delay_shutdown)
        break
    if keyboard.is_pressed('h'):
        time.sleep(delay)
        controls()
        print("\n")
    if keyboard.is_pressed('c'):
        time.sleep(delay)
        rep = input("Enter a custom number of generations: ")
        try:
            for i in range(int(rep)):
                if name == "":
                    name = input("Enter something to generate the name from: ")
                else:
                    print("\n")
                    print("Reversed: " + reverse_mix(name))
                    print("Randomly Mixed: " + rand_mix(name))
                    print("Reversed & Randomly Mixed: " + reversed_rand_mix(name))
                    print("\n************Success!***************")
                    print("Use 'h' to see the controls\n")
        except:
            print("Error! please enter a positive integer and try again")
            print("\n")
    if keyboard.is_pressed('m'):
        time.sleep(delay)
        credit()
        print("\n")

