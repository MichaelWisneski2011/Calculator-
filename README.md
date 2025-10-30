# Calculator-
print("Calculator")

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        return "Error: Cannot divide by zero"
    return a / b
operations_dictionary = {
    "Add": add,
    "Subtract": subtract,
    "Multiply": multiply,
    "Divide": divide
}


while True:
    selection = input("What operation would you like to use (Add, Subtract, Multiply, Divide): ").capitalize()
    if selection in operations_dictionary:
        confirm = input(f"You chose to {selection}. Is that correct? (Yes/No): ").strip().lower()
        if confirm == "yes":
            break
    else:
        print("Invalid selection, try again.")


while True:
    a = input("What is your first number: ")
    try:
        A = float(a)
        break
    except ValueError:
        print("Invalid format, please input a number.")


while True:
    b = input("What is your second number: ")
    try:
        B = float(b)
        break
    except ValueError:
        print("Invalid format, please input a number.")


result = operations_dictionary[selection](A, B)
print(f"Result: {result}")
