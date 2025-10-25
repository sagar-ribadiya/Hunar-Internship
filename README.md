# Hunar-Task-1
Internship
import re

def check_password_strength(password):
    # Criteria checks
    length = len(password) >= 8
    has_upper = re.search(r'[A-Z]', password) is not None
    has_lower = re.search(r'[a-z]', password) is not None
    has_digit = re.search(r'\d', password) is not None
    has_special = re.search(r'[!@#$%^&*(),.?":{}|<>]', password) is not None

    # Score based on criteria
    score = sum([length, has_upper, has_lower, has_digit, has_special])

    # Determine strength
    if score <= 2:
        return "Weak"
    elif score == 3 or score == 4:
        return "Okay"
    else:
        return "Strong"

# Main program
if __name__ == "__main__":
    user_password = input("Enter your password: ")
    strength = check_password_strength(user_password)
    print(f"Password Strength: {strength}")



    *** SAMPLE OUTPUT ****

    Enter your password: Hello123
Password Strength: Okay

Enter your password: Hello@123
Password Strength: Strong

Enter your password: pass
Password Strength: Weak

Features Evaluated
• 	 Minimum length (8 characters)
• 	 Contains uppercase letters
• 	 Contains lowercase letters
• 	 Includes digits
• 	 Has special characters



