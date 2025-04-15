num1 = float(input("Enter the first number: "))
num2 = float(input("Enter the second number: "))
operation = input("Enter the operation (+, -, *, /): ")

if operation == "+":
    result = num1 + num2
    print(f"{num1} + {num2} = {result}")
elif operation == "-":
    result = num1 - num2
    print(f"{num1} - {num2} = {result}")
elif operation == "*":
    result = num1 * num2
    print(f"{num1} * {num2} = {result}")
elif operation == "/":
    if num2 != 0:
        result = num1 / num2
        print(f"{num1} / {num2} = {result}")
    else:
        print("Error! Division by zero.")
else:
    print("Invalid operation.")
def modify_file(input_file, output_file):
    try:
        with open(input_file, "r") as file:
            content = file.read()
        modified_content = content.upper()
        with open(output_file, "w") as file:
            file.write(modified_content)
        print(f"Modified content has been written to {output_file}")
    except FileNotFoundError:
        print(f"The file {input_file} does not exist.")
    except Exception as e:
        print(f"An error occurred: {e}")

def read_file_with_error_handling():
    filename = input("Enter the filename: ")
    try:
        with open(filename, "r") as file:
            content = file.read()
            print("File content:")
            print(content)
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    except IOError:
        print(f"Error: The file '{filename}' can't be read.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

input_file = "input.txt"
output_file = "output.txt"
modify_file(input_file, output_file)
read_file_with_error_handling()
