# If-Else Statement

## Learning Goals

- Continue learning about conditionals.
- Introduce an `if-else` conditional statement.

## Introduction

In the previous lesson we introduced the `if` statement and how a conditional
clause works.

Let's expand on this topic. Say we want to always execute a statement or block
of statements if the conditional clause defined in the `if` statement is always
false. For example, our current `GradeExample` will not print anything if the
student did not pass their test. But maybe we do want to let the user know for
sure that they did not pass their test.

In this lesson, we will introduce the `else` statement.

## If-Else

An `if` statement can be followed by an `else` statement. When an `else`
follows an `if`, its content will be executed whenever the conditional clause
of the `if` statement is not true. It should be noted that an `else` statement
is not required to follow an `if` statement, as we have seen in the example
above. But if we were to have an `else` statement, the syntax would look like
this:

```java
if (true) {
    System.out.println("display this message when true");
} else {
    System.out.println("display this message when false");
}
```

Consider the following flowchart to summarize how an if-else statement works:

![if-else-flowchart](https://curriculum-content.s3.amazonaws.com/java-mod-1/if-else-statement/if-else-conditional-flowchart.png)

### Using the If-Else

Let's modify the program we were working with in the last lesson to include an
`else` statement! Consider the code below with the following changes:

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class GradeExample {
    public static void main (String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            // Prompt the user to enter a numeric grade from 0 to 100
            System.out.println("Enter a numeric grade from 0 - 100:");
            int grade = scanner.nextInt();

            // A passing grade is a 70 or higher
            if (grade >= 70) {
                System.out.println("Congrats! You passed!");
            } else {
                System.out.println("Oops! Better luck next time!");
            }

        } catch (InputMismatchException exception) {
            System.out.println("Invalid input");
        }
    }
}
```

We can take a look at this again with the debugger and the input of `60` again:

![execute-else-block](https://curriculum-content.s3.amazonaws.com/java-mod-1/if-statement/intellij-debugger-else-block-execution.PNG)

As we saw previously, when the program stops and evaluates the conditional
clause, it will return `false` since 60 not greater than or equal to 70. But
this time when we choose the step-over action, the next line to be executed
falls into the `else` block instead of continuing to the end of the program! If
we resume the program, we'll see the following output:

```text
Enter a numeric grade from 0 - 100:
60
Oops! Better luck next time!
```

As we can see, the `else` block changes the flow of the program just slightly
when added. It will always fall into the `else` block if the conditional clause
within the `if` statement evaluates to false.