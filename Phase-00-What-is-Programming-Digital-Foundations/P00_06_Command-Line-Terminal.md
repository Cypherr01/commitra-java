# Topic: Command Line & Terminal  

## What Is This?  
The **command line** (also called a *terminal* or *console*) is a text‑based interface that lets a user talk directly to the operating system.  
Instead of clicking icons, you type a command, press **Enter**, and the OS carries out the request and prints back any result.  
It is the same tool that you will later use to navigate the virtual file system of the “Personal Computer Museum” project.

## How It Works Internally  
1. **You type a line of text** and press **Enter**.  
2. The terminal program sends that line to the operating system as a *request*.  
3. The OS parses the line: it separates the command name, any options (flags), and arguments (such as file names).  
4. The OS looks up the command (a built‑in command or an executable file) and runs it.  
5. The command may read or write files, change the current directory, or simply display information.  
6. Any text the command writes to *standard output* (stdout) is sent back to the terminal, which shows it on the screen.  

Because the OS already knows about **files**, **directories**, and **binary data** (topics you have studied), the command line is just a convenient way to ask the OS to perform those low‑level actions for you.

## Syntax and Structure  
A command line statement follows a very simple pattern:

```
command [option] [argument]
```

* **command** – the name of the operation (e.g., `cd`, `ls`, `mkdir`).  
* **option** – optional flags that modify the command’s behavior (e.g., `-l`).  
* **argument** – data the command works on, such as a file or directory name.

Below is a tiny Java program that mimics this pattern: it reads one line you type, splits it into the three parts, and prints them back. No loops or conditionals are used—only concepts you already know (classes, methods, `System.out`, and `Scanner`).

```java
import java.util.Scanner;

/*  SimpleCommandLine
 *  Demonstrates the basic “command option argument” pattern.
 *  The program reads ONE line from the user, separates it by spaces,
 *  and prints the three pieces (if they exist).
 */
public class SimpleCommandLine {
    public static void main(String[] args) {
        // Create a scanner that reads from the keyboard (standard input)
        Scanner scanner = new Scanner(System.in);

        // Prompt the user – this is what you see in a real terminal
        System.out.print("> ");

        // Read the whole line the user typed
        String line = scanner.nextLine();          // e.g. "ls -l Documents"

        // Split the line on spaces; the result is an array of words
        String[] parts = line.split(" ");

        // Show what was entered, piece by piece
        System.out.println("Command : " + parts[0]);               // always present
        if (parts.length > 1) {
            System.out.println("Option  : " + parts[1]);           // may be missing
        }
        if (parts.length > 2) {
            System.out.println("Argument: " + parts[2]);           // may be missing
        }

        // Close the scanner (good practice)
        scanner.close();
    }
}
```

*The comments (`/* … */` and `// …`) explain each line for a beginner.*

## Practical Example  
Imagine you are using a real terminal on a Unix‑like system:

```
> cd Documents
```

* `cd` – command that changes the current directory.  
* No option is needed.  
* `Documents` – argument telling the OS *which* directory to move into.

If you typed the same line into the Java program above, it would output:

```
Command : cd
Argument: Documents
```

## Common Mistakes Beginners Make  

| Mistake | What It Looks Like (what NOT to do) | Why It Fails |
|---------|--------------------------------------|--------------|
| **1. Forget the space between command and argument** | `cdDocuments` | The OS treats the whole string as a single command name, which does not exist. |
| **2. Use the wrong case** (commands are case‑sensitive) | `LS -l` | `LS` is not the same as `ls`; the OS cannot find a command named `LS`. |
| **3. Omit the required argument** | `cd` (without a directory) | `cd` needs to know *where* to go; without an argument the OS reports an error. |

## Programming Challenge  
Write a Java program that behaves like a very tiny command line:

1. Display a prompt (`> `).  
2. Read ONE line of input from the user.  
3. Echo the line back prefixed with “You typed:”.  

*Do not add loops or extra features yet – just a single read‑and‑print.*

## Solution  
```java
import java.util.Scanner;

public class EchoCommand {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("> ");               // show the prompt
        String userInput = scanner.nextLine(); // read one line

        System.out.println("You typed: " + userInput); // echo it back

        scanner.close(); // tidy up
    }
}
```

Running this program produces:

```
> hello world
You typed: hello world
```

## What Comes Next  
Now that you understand **what a terminal is**, **how a command is structured**, and have built a tiny Java “read‑and‑echo” tool, the next topic will introduce **basic command‑line navigation** (`cd`, `ls`, `pwd`) and show how to manipulate a *real* file system from Java using the `java.io.File` class. Those concepts will let you start building the interactive command line for the Personal Computer Museum project.