## Conditional Statements in Linux Shell Scripting

In Linux shell scripting, `if-elif-else` statements are used to make decisions based on certain conditions. These statements allow you to control the flow of your script based on whether a given condition is true or false.

### 1. Basic Syntax

The basic syntax of an `if-elif-else` statement in bash is as follows:

```bash
if [ condition ]; then
    # code to be executed if the condition is true
elif [ another_condition ]; then
    # code to be executed if the another_condition is true
else
    # code to be executed if none of the conditions are true
fi
```

### 2. Examples

#### 2.1. Simple Numeric Comparison

```bash
#!/bin/bash

number=5

if [ $number -eq 5 ]; then
    echo "The number is 5."
elif [ $number -gt 5 ]; then
    echo "The number is greater than 5."
else
    echo "The number is less than 5."
fi
```

#### 2.2. String Comparison

```bash
#!/bin/bash

word="Linux"

if [ "$word" == "Linux" ]; then
    echo "The word is Linux."
elif [ "$word" == "Unix" ]; then
    echo "The word is Unix."
else
    echo "The word is neither Linux nor Unix."
fi
```

#### 2.3. File Existence Check

```bash
#!/bin/bash

file_path="/path/to/somefile.txt"

if [ -e "$file_path" ]; then
    echo "The file exists."
else
    echo "The file does not exist."
fi
```

#### 2.4. Logical AND and OR

```bash
#!/bin/bash

age=25

if [ $age -ge 18 ] && [ $age -le 30 ]; then
    echo "You are between 18 and 30 years old."
elif [ $age -lt 18 ] || [ $age -gt 30 ]; then
    echo "You are either under 18 or over 30 years old."
else
    echo "Invalid age."
fi
```

### 3. Notes

- Ensure proper spacing and quoting in conditions to avoid syntax errors.
- Use appropriate comparison operators (`-eq`, `-ne`, `-lt`, `-le`, `-gt`, `-ge`) for numeric comparisons.
- For string comparisons, use `==`.
- File-related conditions, such as `-e` for existence, can be useful in script logic.

# Case Statements in Linux Shell Scripting

In Linux shell scripting, the `case` statement is a powerful tool for handling multiple conditions in a more readable and structured way. It provides an alternative to a series of `if-elif-else` statements when dealing with different values of a variable.

## 1. Basic Syntax

The basic syntax of a `case` statement in bash is as follows:

```bash
case variable in
    pattern1)
        # code to be executed if variable matches pattern1
        ;;
    pattern2)
        # code to be executed if variable matches pattern2
        ;;
    pattern3)
        # code to be executed if variable matches pattern3
        ;;
    *)
        # code to be executed if variable matches none of the patterns
        ;;
esac
```

## 2. Example Usage

### 2.1. Simple Case Statement

```bash
#!/bin/bash

fruit="apple"

case $fruit in
    "apple")
        echo "It's a delicious apple."
        ;;
    "orange")
        echo "It's a juicy orange."
        ;;
    "banana")
        echo "It's a ripe banana."
        ;;
    *)
        echo "Unknown fruit."
        ;;
esac
```

### 2.2. Case Statement with Pattern Ranges

```bash
#!/bin/bash

score=85

case $score in
    [90-100])
        echo "Excellent! You scored an A."
        ;;
    [80-89])
        echo "Good job! You scored a B."
        ;;
    [70-79])
        echo "Not bad. You scored a C."
        ;;
    *)
        echo "You need to improve."
        ;;
esac
```

### 2.3. Case Statement with Wildcards

```bash
#!/bin/bash

file="example.txt"

case $file in
    *.txt)
        echo "It's a text file."
        ;;
    *.pdf)
        echo "It's a PDF document."
        ;;
    *)
        echo "Unknown file type."
        ;;
esac
```

## 3. Notes

- Each pattern should end with `;;` to indicate the end of that particular case.
- The `*)` at the end serves as the default case, similar to the `else` statement in `if-elif-else` constructs.
- Use of square brackets allows for pattern matching using ranges or wildcards.


