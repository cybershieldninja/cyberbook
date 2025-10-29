## User Define Variables

- A variable is a character string to which we assign a value.
- A variable is nothing more than a pointer to the actual data. The shell enables you to create, assign, and delete variables.


## Rules:

- The name of a variable can contain only letters (a to z or A to Z), numbers ( 0 to 9) or the underscore character ( _ ).
- Variable names cannot be reserved words
- Variable names cannot have whitespace in between
- The variable name cannot have special characters.
- The first character of the variable name cannot be a number.
- By convention, Unix shell variables will have their names in UPPERCASE.


### The following examples are valid variable names −

```bash
_VARIABLE_NAME
VARIABLE_NAME
VARIABLE_1_NAME
vARIABLE_2_NAME
```

### Following are the examples of invalid variable names −

```bash
2_VARNAME
-VARIABLENAME
VARIABLENAME-SOMENAME
SOMENAME_A!
```

- The reason you cannot use other characters such as !, *, or - is that these characters have a special meaning for the shell.



## Declaring and Using Variables in Linux

In Linux, you can declare variables without specifying their data types. Variables are case-sensitive, and conventionally, they are written in uppercase.

```bash
# Declare a variable
MY_VARIABLE="Hello, Linux!"

# Declare a numeric variable
NUM_VAR=42
```

- Note that there must be no spaces around the "=" sign: VAR=value works; VAR = value doesn't work. In the first case, the shell sees the "=" symbol and treats the command as a variable assignment. In the second case, the shell assumes that VAR must be the name of a command and tries to execute it.

## Variable Assignment

You can assign values to variables using the equal sign (`=`). No spaces are allowed around the equal sign.

```bash
# Assign a new value to an existing variable
MY_VARIABLE="New value"
```

## Variable Usage

To use the value stored in a variable, precede the variable name with a dollar sign (`$`).

```bash
# Use the value of a variable
echo $MY_VARIABLE
```

## Command Substitution

You can use command substitution to assign the output of a command to a variable.

```bash
# Command substitution
CURRENT_DATE=$(date)
echo "Today's date is: $CURRENT_DATE"
```

## Special Variables

Linux has some special variables that provide information about the environment.

```bash
# Special variables
echo "Script name: $0"
echo "Number of arguments: $#"
echo "All arguments: $@"
echo "Exit status of the last command: $?"
```

## Readonly Variables

You can make a variable read-only to prevent it from being changed later.

```bash
# Readonly variable
readonly READ_ONLY_VAR="This is a read-only variable"
```

## System Variable in Shell Script

System variables in a Linux bash shell are created and maintained by the shell itself. These variables, with the exception of `auto_resume` and `histchars`, are defined in CAPITAL LETTERS. Configuration of the shell can be customized by modifying system variables such as `PS1`, `PATH`, `LANG`, `HISTSIZE`, and `DISPLAY`, among others.

There are several commands available for listing and setting environment variables in Linux:

- `env`: Allows you to run another program in a custom environment without modifying the current one. When used without an argument, it prints a list of the current environment variables.
- `printenv`: Prints all or the specified environment variables.
- `set`: Sets or unsets shell variables. When used without an argument, it prints a list of all variables, including environment and shell variables, and shell functions.
- `unset`: Deletes shell and environment variables.
- `export`: Sets environment variables.

## Common Environment Variables

- `USER`: The current logged-in user.
- `HOME`: The home directory of the current user.
- `EDITOR`: The default file editor to be used. This is the editor that will be used when you type `edit` in your terminal.
- `SHELL`: The path of the current user’s shell, such as bash or zsh.
- `LOGNAME`: The name of the current user.
- `PATH`: A list of directories to be searched when executing commands. When you run a command, the system will search those directories in this order and use the first found executable.
- `LANG`: The current locales settings.
- `TERM`: The current terminal emulation.


# Numeric Operations in Linux

In Linux, the command-line interface provides powerful tools for performing numeric operations. Whether you need to perform basic arithmetic, more advanced calculations, or manipulate numerical data in files, Linux has the tools to get the job done.

## 1. Basic Arithmetic Operations

### 1.1. Addition

To add two numbers, you can use the `expr` command or the `$(( ))` construct.

```bash
result=$(expr 5 + 3)
echo "5 + 3 equals $result"
# or
result=$((5 + 3))
echo "5 + 3 equals $result"
```

### 1.2. Subtraction

Similarly, subtraction can be done using `expr` or `$(( ))`.

```bash
result=$(expr 8 - 2)
echo "8 - 2 equals $result"
# or
result=$((8 - 2))
echo "8 - 2 equals $result"
```

### 1.3. Multiplication

Multiplication is achieved using the `expr` command.

```bash
result=$(expr 4 \* 6)
echo "4 * 6 equals $result"
```

Note: The `*` needs to be escaped with a backslash (`\`) to prevent it from being interpreted as a wildcard character.

### 1.4. Division

Division can also be performed using `expr`.

```bash
result=$(expr 15 / 3)
echo "15 / 3 equals $result"
```

## 2. Advanced Arithmetic with `bc`

For more complex mathematical calculations, the `bc` command is a powerful tool. It supports floating-point arithmetic and mathematical functions.

### 2.1. Installation

If not installed, you can install `bc` using the package manager for your distribution.

```bash
# For Debian/Ubuntu
sudo apt-get install bc

# For Red Hat/Fedora
sudo dnf install bc
```

### 2.2. Example Usage

```bash
echo "scale=2; 7 / 3" | bc
# Outputs: 2.33
```

The `scale` parameter sets the number of decimal places.

## 3. Numeric Manipulation in Files

Linux provides commands to perform numeric operations on data within files.

### 3.1. `awk` for Numeric Operations in Files

```bash
# Sum the values in the second column of a space-separated file
awk '{sum += $2} END {print sum}' data.txt
```

### 3.2. `sed` for Basic Arithmetic in Files

```bash
# Multiply each number in a file by 2
sed 's/[0-9]\+/\n&\n/2;s/\n//;s/\([0-9]\+\)\(.*\)\([0-9]\+\)/\1*\3/' data.txt
```

 Adjust the commands according to your specific needs and file formats.

These are just a few examples of numeric operations in Linux. Depending on your requirements, you may need to combine these tools or explore additional commands for more advanced calculations.


# **String Manipulation in Linux**

String manipulation is a crucial aspect of working with the Linux command line. Whether you're dealing with file names, text data, or command outputs, understanding how to manipulate strings can greatly enhance your efficiency. In this tutorial, we will explore some fundamental string manipulation techniques in Linux.

## 1. **Variable Assignment**

In bash scripting, you often deal with variables. To assign a string to a variable, use the following syntax:

```bash
```bash
string_variable="Hello, Linux!"
echo $string_variable
```

## 2. **Concatenation**

To concatenate strings, you can use the concatenation operator `+` or simply place the strings next to each other:

```bash
string1="Hello"
string2="Linux"
concatenated_string=$string1$string2
echo $concatenated_string
```

## 3. **Substring Extraction**

Extracting a portion of a string can be done using the `${string: start_index: length}` syntax. Here's an example:

```bash
original_string="Linux_is_awesome"
substring=${original_string:6:2}
echo $substring
```

This will output `is`, starting from index 6 with a length of 2.

## 4. **String Length**

To find the length of a string, use the `${#string}` syntax:

```bash
my_string="Linux"
length=${#my_string}
echo "Length of the string is $length"
```

## 5. **Searching and Replacing**

### Searching
To find the position of a substring within a string, use the `expr` command:

```bash
full_string="Linux is powerful and flexible"
substring="powerful"
position=$(expr index "$full_string" "$substring")
echo "Substring found at position $position"
```

### Replacing
To replace a substring within a string, use parameter expansion:

```bash
original_string="I love Linux"
new_string=${original_string/Linux/Ubuntu}
echo $new_string
```

## 6. **Pattern Matching**

Pattern matching allows you to check if a string matches a specific pattern. The `[[ ]]` construct is often used for pattern matching:

```bash
string="Linux123"
if [[ $string =~ ^[A-Za-z]+$ ]]; then
    echo "String contains only letters."
else
    echo "String contains non-letter characters."
fi
```
