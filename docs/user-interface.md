## Interface

### File `main.py`

#### `menu()`

```python
def menu():
    """
    Displays the menu options for the user.
    The menu includes options to display a random quote, display a specified
    number of quotes, add a new quote, and exit the program.
    Returns:
    None
    """
    print("\n==== Programming Quotes ====")
    print("random : Random quote")
    print("display : Display quotes")
    print("add : Add a new quote")
    print("exit : Exit the program")
def main():
    """
    Main function to run the program.
    It loads quotes from a file, displays the menu, and processes user input
    to perform actions based on the user's choice.
    Returns:
    None
    """
    while True:
        quotes = load_quotes("quotes.txt")
        menu()

        choice = input(">> ")

        if choice == "random":
            print_quote(random_quote(quotes))
        elif choice == "display":
            count = int(input("Enter the number of quotes to display: "))
            display_quotes(quotes, count)
        elif choice == "add":
            add_quote(quotes, "quotes.txt")
        elif choice == "exit":
            print("Good bye...")
            break
        else:
            print("Invalid input")
