import math

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    else:
        return x / y

def power(x, y):
    return math.pow(x, y)

def sqrt(x):
    if x < 0:
        return "Error! Square root of negative number."
    else:
        return math.sqrt(x)

def log(x):
    if x <= 0:
        return "Error! Logarithm of non-positive number."
    else:
        return math.log(x)

def sin(x):
    return math.sin(math.radians(x))

def cos(x):
    return math.cos(math.radians(x))

def tan(x):
    return math.tan(math.radians(x))

def advanced_calculator():
    print("Select operation:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Power (x^y)")
    print("6. Square Root")
    print("7. Logarithm")
    print("8. Sine")
    print("9. Cosine")
    print("10. Tangent")

    while True:
        choice = input("Enter choice (1-10): ")

        if choice in ['1', '2', '3', '4', '5']:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
            except ValueError:
                print("Invalid input! Please enter a number.")
                continue

            if choice == '1':
                print(f"{num1} + {num2} = {add(num1, num2)}")
            elif choice == '2':
                print(f"{num1} - {num2} = {subtract(num1, num2)}")
            elif choice == '3':
                print(f"{num1} * {num2} = {multiply(num1, num2)}")
            elif choice == '4':
                result = divide(num1, num2)
                print(f"{num1} / {num2} = {result}")
            elif choice == '5':
                print(f"{num1} ^ {num2} = {power(num1, num2)}")

        elif choice == '6':
            try:
                num = float(input("Enter a number: "))
            except ValueError:
                print("Invalid input! Please enter a number.")
                continue
            print(f"√{num} = {sqrt(num)}")

        elif choice == '7':
            try:
                num = float(input("Enter a number: "))
            except ValueError:
                print("Invalid input! Please enter a number.")
                continue
            print(f"log({num}) = {log(num)}")

        elif choice in ['8', '9', '10']:
            try:
                angle = float(input("Enter angle in degrees: "))
            except ValueError:
                print("Invalid input! Please enter a number.")
                continue

            if choice == '8':
                print(f"sin({angle}) = {sin(angle)}")
            elif choice == '9':
                print(f"cos({angle}) = {cos(angle)}")
            elif choice == '10':
                print(f"tan({angle}) = {tan(angle)}")

        # Ask if the user wants to perform another calculation
        next_calc = input("Do you want to perform another calculation? (yes/no): ")
        if next_calc.lower() != 'yes':
            break
        else:
            print("\n")

if __name__ == "__main__":
    advanced_calculator()