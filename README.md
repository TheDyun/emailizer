# emailizer
turn a list of full names into emails with the domain and format of your choice

import sys

#introduction
print("------------------------------------------------------------------------------------------")
print("Thank you for using Emailizer by the Dyun\n")
print("To use this tool, you must make sure that your textfile lists names in the following format. (firstname lastname)")
print("The syntax for using Emailizer: python3 emailizer.py <namelist.txt> <output email list.txt")

print("------------------------------------------------------------------------------------------")

#email format
emailstructure = input("""
Please specify the desired email format:\n\n
Option 1. first name + last name
Option 2. first initial + last name
Option 3. first name + last initial
Option 4. last name + first name 
Option 5. last name + first initial
Option 6. last name initial + first name
\n
""")

print("\nYou have selected Option " + emailstructure)

#domain option
domain = input("And what is the domain? (e.g. gmail.com)\n")


print("\nAlright. Here are your " + str(domain) +" addresses!\n")

#sys.argv
input_filename = sys.argv[1]


#assigning argument as variable and parsing lines
input_file = open(input_filename, 'r') 
input = input_file.readlines()

#email creating loop
length = len(input) 
for x in range (length):
    name = input[x].split(" ") 
    firstname = name[0]
    if x == length-1:
        lastname = name[1]
    else:
        lastname = name[1][:-1] 
    if emailstructure == ("1"):
        print(firstname+lastname+"@"+domain)
    elif emailstructure == ("2"):
        print(firstname[0]+lastname+"@"+domain)
    elif emailstructure == ("3"):
        print(firstname+lastname[0]+"@"+domain)
    elif emailstructure == ("4"):
        print(lastname+firstname+"@"+domain)
    elif emailstructure == ("5"):
        print(lastname+firstname[0]+"@"+domain)
    else:
        print(lastname[0]+firstname+"@"+domain)
print("\nThank you for using Emailizer")
print("------------------------------------------------------------------------------------------")

        




