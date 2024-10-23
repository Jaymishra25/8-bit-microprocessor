# 8-bit-microprocessor
class Microcontroller8Bit:
    def __init__(self):
        self.register = 0  # Initialize register to 0

    def load_value(self, value):
        """Load an 8-bit value (0-255) into the register."""
        if 0 <= value <= 255:
            self.register = value
            print(f"Loaded value: {self.register}")
        else:
            print("Error: Value must be between 0 and 255.")

    def add(self, value):
        """Add an 8-bit value to the register."""
        if 0 <= value <= 255:
            result = (self.register + value) & 0xFF  # Ensure result is 8 bits
            self.register = result
            print(f"Added value: {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 255.")

    def subtract(self, value):
        """Subtract an 8-bit value from the register."""
        if 0 <= value <= 255:
            result = (self.register - value) & 0xFF  # Ensure result is 8 bits
            self.register = result
            print(f"Subtracted value: {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 255.")

    def bitwise_and(self, value):
        """Perform bitwise AND operation."""
        if 0 <= value <= 255:
            result = self.register & value
            self.register = result
            print(f"Bitwise AND with value: {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 255.")

    def bitwise_or(self, value):
        """Perform bitwise OR operation."""
        if 0 <= value <= 255:
            result = self.register | value
            self.register = result
            print(f"Bitwise OR with value: {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 255.")

    def display_register(self):
        """Display the current value in the register."""
        print(f"Current register value: {self.register}")

def main():
    mc = Microcontroller8Bit()

    while True:
        print("\nMicrocontroller 8-Bit Simulator")
        print("1. Load Value")
        print("2. Add Value")
        print("3. Subtract Value")
        print("4. Bitwise AND")
        print("5. Bitwise OR")
        print("6. Display Register")
        print("7. Exit")

        choice = input("Choose an option: ")

        if choice == '1':
            value = int(input("Enter an 8-bit value (0-255): "))
            mc.load_value(value)
        elif choice == '2':
            value = int(input("Enter a value to add (0-255): "))
            mc.add(value)
        elif choice == '3':
            value = int(input("Enter a value to subtract (0-255): "))
            mc.subtract(value)
        elif choice == '4':
            value = int(input("Enter a value for bitwise AND (0-255): "))
            mc.bitwise_and(value)
        elif choice == '5':
            value = int(input("Enter a value for bitwise OR (0-255): "))
            mc.bitwise_or(value)
        elif choice == '6':
            mc.display_register()
        elif choice == '7':
            print("Exiting...")
            break
        else:
            print("Invalid option. Please try again.")

if __name__ == "__main__":
    main()
