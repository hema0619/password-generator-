# password-generator-
the project generates strong random passwords based on user-selected criteria 
import random
import string

def generate_password(length, use_upper, use_lower, use_digits, use_symbols):
    characters = ""

    if use_upper:
        characters += string.ascii_uppercase
    if use_lower:
        characters += string.ascii_lowercase
    if use_digits:
        characters += string.digits
    if use_symbols:
        characters += string.punctuation

    if not characters:
        return "Error: No character set selected!"

    password = ''.join(random.choice(characters) for _ in range(length))
    return password


print("🔐 PASSWORD GENERATOR 🔐")

length = int(input("Enter password length: "))

use_upper = input("Include uppercase letters? (y/n): ").lower() == 'y'
use_lower = input("Include lowercase letters? (y/n): ").lower() == 'y'
use_digits = input("Include numbers? (y/n): ").lower() == 'y'
use_symbols = input("Include special characters? (y/n): ").lower() == 'y'

password = generate_password(length, use_upper, use_lower, use_digits, use_symbols)

print("\nGenerated Password:", password) 
