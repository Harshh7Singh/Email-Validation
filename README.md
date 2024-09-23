# Email-Validation
This project provides a Python-based solution for validating email addresses using regular expressions. It verifies the structure of email addresses and checks for common formatting errors, such as missing @ symbols, invalid characters, and domain issues.

#USING STRING METHOD
email = input("Enter your Email: ")  # Example: g@g.in
k, j, d = 0, 0, 0

if len(email) >= 6:
    if email[0].isalpha():
        if "@" in email and email.count("@") == 1:
            if email[-4] == "." or email[-3] == ".":  # Correcting the XOR operator for email domain check
                for i in email:
                    if i.isspace():
                        k = 1
                    elif i.isalpha():
                        if i.isupper():
                            j = 1
                    elif i.isdigit():
                        continue
                    elif i == "_" or i == "." or i == "@":
                        continue
                    else:
                        d = 1

                if k == 1 or j == 1 or d == 1:
                    print("Wrong Email 5")
                else:
                    print("Right Email")
            else:
                print("Wrong Email 4")
        else:
            print("Wrong Email 3")
    else:
        print("Wrong Email 2")
else:
    print("Wrong Email 1")


#USING REGULAR EXPRESSION IN THIS YOU SHOULD IMPORT REGEX MODUL

import re
email_condition = "^[a-z]+[\._]?[a-z 0-9]+[@]\w+[.]\w{2,3}$"
user_email = input("Enter a email :")
if re.search(email_condition,user_email):
    print("Right Email")
else:
    print("Wrong Email ")
