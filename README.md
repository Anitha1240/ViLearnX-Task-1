# ViLearnX-Task-1
def letter_to_grade(letter):
    letter = letter.upper()
    if letter == 'A':
        return 10.0
    elif letter == 'B':
        return 9.0
    elif letter == 'C':
        return 8.0
    elif letter == 'D':
        return 7.0
    elif letter == 'E':
        return 6.0
    elif letter == 'F':
        return 0.0
    else:
        return None

def calculate_average(grades):
    if not grades:
        return 0
    return sum(grades) / len(grades)

def main():
    print("Welcome to the Student Grade Tracker!")
    
  # Ask for the number of grades
   while True:
        try:
            num_grades = int(input("How many grades do you want to enter? "))
            if num_grades > 0:
                break
            else:
                print("Please enter a positive number.")
        except ValueError:
            print("Invalid input. Please enter a numeric value.")

  grades = []
    
  for i in range(num_grades):
        while True:
            grade_input = input(f"Enter grade {i + 1} (A, B, C, D, E, F): ")
            numeric_grade = letter_to_grade(grade_input)
            if numeric_grade is not None:
                grades.append(numeric_grade)
                break
            else:
                print("Invalid grade. Please enter a letter grade (A-F).")

  if grades:
        average = calculate_average(grades)
       # Convert average to letter grade
        if average >= 9.5:
            letter = 'A'
        elif average >= 8.5:
            letter = 'B'
        elif average >= 7.5:
            letter = 'C'
        elif average >= 6.5:
            letter = 'D'
        elif average >= 5.5:
            letter = 'E'
        else:
            letter = 'F'
        print("\n--- Grade Summary ---")
        print(f"Grades entered: {[['A', 'B', 'C', 'D', 'E', 'F'][int(g) - 6] for g in grades]}")
        print(f"Average Grade (Numeric): {average:.2f}")
        print(f"Letter Grade: {letter}")
else:
        print("No grades entered.")

if __name__ == "__main__":
    main()
