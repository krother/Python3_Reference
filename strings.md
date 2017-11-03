
# String

Text values are called **strings**. In Python, strings are defined by single quotes, double quotes or three quotes of either. The following string assignments are equivalent:

    first = 'Emily'
    first = "Emily"
    first = '''Emily'''
    first = """Emily"""

## Special characters

Some characters in Python require special attention:

* **Newline characters** - writing `\n` into a string stands for the beginning of a new line.
* **Tabulators** - writing `\t` into a string stands for a tabulator.
* **Backslashes** - because the backslash (`\`) has a special meaning in the above, you need to write a double backslash (`\\`) to represent a single backslash.
* **Language-specific characters** - Python 3 stores **Unicode** characters including German Umlauts, Chinese and Arab alphabets by default. However, they may be interpreted in the same way in different environments. Just be a bit careful when using them.

## String concatenation

The operator `+` also works for strings, only that it concatenates the strings. It does not matter whether you write the strings as variables or as explicit values.

With `first = 'Emily'` and `last = 'Smith'` the following three statements have the same result:

    name = first + last
    name = first + "Smith"
    name = "Emily" + "Smith"


## Accessing single characters

Using square brackets, any character of a string can be accessed. This is called **indexing**. The first character has the index `[0]`, the second `[1]` and the fourth has the index `[3]`.

    name[0]
    name[3]

With negative numbers, you can access single characters from the end, the index `[-1]` being the last, `[-2]` the second last character and so on:

    name[-1] 
    name[-2] 

Note that none of these modify the contents of the string variable.


## Creating substrings

Substrings can be formed by applying square brackets with two numbers inside separated by a colon (slices). The second number is not included in the substring itself.

    name = 'Emily Smith'
    name[0:5]
    name[1:4]
    name[6:11]
    name[:3] 
    name[-4:] 


## String methods

Every string in Python brings a list of functions to work with it. As the functions are contained within the string they are also called **methods**. They are used by adding the `.` to the string variable followed by the method name.

Below you find a few of the available methods:

### Changing case

    name = 'Manipulating Strings \n'
    name.upper()
    name.lower()

### Removing whitespace at both ends

    name.strip()

### Cutting a string into columns

    name.split(' ')

### Searching for substrings

    name.find('ing')

The method returns the start index of the match. The result -1 means that no match has been found.

### Replacing substrings

    name.replace('Strings','text')

### Checking beginning and end of a string

Both of the following functions return a boolean:

    name.startswith('Man')
    name.endswith('ings') 
