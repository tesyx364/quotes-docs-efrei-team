## Core functions

### File `functions.py`

#### `load_quotes(filename)`

```python
def load_quotes(filename):
    """
    Loads quotes from a file and returns them as a list.
    Parameters:
    filename (str): The path to the file containing quotes.
    The function reads the file line by line, strips whitespace, and appends
    non-empty lines to a list. Each line in the file should contain one quote.
    Returns:
    list: A list of quotes loaded from the file.
    Example:
    load_quotes('quotes.txt')
    This function reads the file 'quotes.txt' and returns a list of quotes.
    """
    quotes = []
    with open(filename, 'r') as file:
        lines = file.readlines()
    for line in lines:
        line = line.strip()
        if line:
            quotes.append(line)
    return quotes

def random_quote(quotes):
    """
    Returns a random quote from the provided list of quotes.
    Parameters:
    quotes (list): A list of quotes from which a random quote will be selected.
    The function uses the random.choice() method to select a random quote.
    Returns:
    str: A randomly selected quote from the list.
    Example:
    random_quote(['Quote 1', 'Quote 2', 'Quote 3'])
    This function returns a random quote from the provided list.
    """  
    random_quote = random.choice(quotes)
    return random_quote

def print_quote(quote):
    """
    Prints a single quote to the console.
    Parameters:
    quote (str): The quote to be printed.
    The function formats the quote with asterisks and prints it to the console.
    Returns:
    None
    Example:
    print_quote('This is a quote.')
    """
print(quote)

def view_quotes(quotes):
    """
    Prints all quotes in the provided list to the console.
    Parameters:
    quotes (list): A list of quotes to be printed.  
    The function iterates through the list and prints each quote using the
    Returns:
    None
    Example:
    view_quotes(['Quote 1', 'Quote 2', 'Quote 3'])
    This function prints each quote in the provided list.
    """
    for quote in quotes:
        print_quote(quote)

def add_quote(quotes, filename):
    """
    Adds a new quote to the list of quotes and appends it to a file.
    Parameters:
    quotes (list): A list of existing quotes to which the new quote will be added.
    filename (str): The path to the file where the new quote will be appended.
    The function prompts the user to input a new quote, appends it to the provided
    list of quotes, and writes it to the specified file. Each quote is written on
    a new line in the file.
    Returns:
    None
    Example:
    add_quote(['Quote 1', 'Quote 2'], 'quotes.txt')
    """
    new_quote = input("Enter a new quote: ")
    quotes.append(new_quote)
    with open(filename, 'a') as file:
        file.write(new_quote)
        file.write('\n')
    print("Quote added successfully!")

def display_quotes(quotes, count):
    """
    Displays a specified number of quotes from the provided list.
    Parameters:
    quotes (list): A list of quotes to be displayed.
    count (int): The number of quotes to display. If count is greater than the
    length of the list, all quotes will be displayed.
    The function checks if the count is valid and prints the specified number
    of quotes. If the count exceeds the number of available quotes, it prints
    all quotes.
    Returns:
    None
    Example:
    display_quotes(['Quote 1', 'Quote 2', 'Quote 3'], 2)
    This function prints the first 2 quotes from the provided list.
    """
    if count >= len(quotes):
        print("All Quotes:")
        view_quotes(quotes)
    else:
        print(f"First {count} Quotes:")
        for i in range(count):
            print_quote(quotes[i])
