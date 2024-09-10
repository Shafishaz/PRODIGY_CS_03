import re

def assess_password_strength(password):
    # Initialize strength variables
    length_score = 0
    upper_case_score = 0
    lower_case_score = 0
    number_score = 0
    special_char_score = 0
    
    # Criteria for password strength
    if len(password) >= 8:
        length_score = 1
    if len(password) >= 12:
        length_score = 2

    if re.search(r'[A-Z]', password):
        upper_case_score = 1

    if re.search(r'[a-z]', password):
        lower_case_score = 1

    if re.search(r'\d', password):
        number_score = 1

    if re.search(r'[@$!%*?&#]', password):
        special_char_score = 1

    # Calculate total score
    total_score = length_score + upper_case_score + lower_case_score + number_score + special_char_score

    # Determine password strength and provide feedback
    if total_score == 5:
        strength = "Very Strong"
        feedback = "Your password is very strong!"
    elif total_score >= 4:
        strength = "Strong"
        feedback = "Your password is strong. Consider adding more special characters or numbers for added security."
    elif total_score >= 3:
        strength = "Medium"
        feedback = "Your password is of medium strength. Consider adding uppercase letters, numbers, or special characters."
    elif total_score >= 2:
        strength = "Weak"
        feedback = "Your password is weak. Consider increasing its length and adding a mix of character types."
    else:
        strength = "Very Weak"
        feedback = "Your password is very weak. It should be longer and include uppercase, lowercase, numbers, and special characters."

    return {
        "strength": strength,
        "feedback": feedback
    }

# Example usage
password = input("Enter a password to assess its strength: ")
result = assess_password_strength(password)
print(f"Password Strength: {result['strength']}")
print(f"Feedback: {result['feedback']}")
