# **Loops in Linux**

## 1. For Loop

The `for` loop in Bash is used to iterate over a sequence of values. It has the following syntax:

```bash
for variable in sequence
do
    # Commands to be executed for each iteration
done
```

- **`variable`**: Represents the loop variable that takes each value in the specified sequence.
- **`sequence`**: Can be a range of numbers, a list of items, or the output of a command.

Example:

```bash
for i in {1..5}
do
    echo "Iteration $i"
done
```

This will print:

```
Iteration 1
Iteration 2
Iteration 3
Iteration 4
Iteration 5
```

## 2. While Loop

The `while` loop in Bash continues to execute a block of commands as long as a specified condition is true. Here is the basic syntax:

```bash
while [ condition ]
do
    # Commands to be executed as long as the condition is true
done
```

- **`condition`**: Represents the test that determines whether the loop continues or terminates.

Example:

```bash
counter=1
while [ $counter -le 5 ]
do
    echo "Iteration $counter"
    ((counter++))
done
```

This will print the same output as the previous `for` loop example.

## 3. Until Loop

The `until` loop is similar to the `while` loop, but it continues to execute a block of commands as long as a specified condition is false. The syntax is as follows:

```bash
until [ condition ]
do
    # Commands to be executed as long as the condition is false
done
```

Example:

```bash
counter=1
until [ $counter -gt 5 ]
do
    echo "Iteration $counter"
    ((counter++))
done
```

# **Loop Control Statements in Linux**

## 1. Break Statement

The `break` statement in Bash is used to exit a loop prematurely based on a certain condition. It is typically used to terminate a loop when a specific condition is met. Here is the basic syntax:

```bash
while [ condition ]
do
    # Commands to be executed
    if [ some_condition ]
    then
        break
    fi
done
```

- **`condition`**: Represents the loop's main condition.
- **`some_condition`**: A condition that, when true, triggers the `break` statement, causing the loop to terminate.

Example:

```bash
counter=1
while [ $counter -le 10 ]
do
    echo "Iteration $counter"
    if [ $counter -eq 5 ]
    then
        break
    fi
    ((counter++))
done
```

This loop will print the numbers from 1 to 5 and then exit due to the `break` statement.

## 2. Continue Statement

The `continue` statement in Bash is used to skip the rest of the commands within a loop for the current iteration and move on to the next iteration. It is useful when you want to bypass specific iterations based on a condition. The syntax is as follows:

```bash
while [ condition ]
do
    # Commands to be executed
    if [ some_condition ]
    then
        continue
    fi
    # More commands that will be skipped if the continue statement is triggered
done
```

- **`condition`**: Represents the loop's main condition.
- **`some_condition`**: A condition that, when true, triggers the `continue` statement, skipping the remaining commands for the current iteration.

Example:

```bash
for i in {1..5}
do
    if [ $i -eq 3 ]
    then
        continue
    fi
    echo "Iteration $i"
done
```