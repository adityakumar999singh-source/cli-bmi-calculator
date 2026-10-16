# cli-bmi-calculator
A modular,  production-ready Command-Line Interface (CLI) application built in Python to compute Body Mass Index (BMI) and determine WHO health classifications with rigorous input validation and error handling.

while True:
    print("\n--- New BMI Calculation ---")
    
    # Input validation
    try:
        weight = float(input("Enter weight (kg) or type a negative number to quit: "))
        if weight < 0:
            print("Exiting program.")
            break
        elif weight == 0:
            print("Weight cannot be zero.")
            continue
            
        height = float(input("Enter height (m): "))
        if height <= 0:
            print("Height must be greater than zero.")
            continue
    except ValueError:
        print("Invalid character entered. Start over.")
        continue

    # Calculation and logic
    bmi = weight / (height ** 2)
    
    if bmi < 18.5:
        cat = "Underweight"
    elif bmi <= 24.9:
        cat = "Normal"
    elif bmi <= 29.9:
        cat = "Overweight"
    else:
        cat = "Obese"

    print(f"Calculated BMI: {bmi:.2f} ({cat})")
