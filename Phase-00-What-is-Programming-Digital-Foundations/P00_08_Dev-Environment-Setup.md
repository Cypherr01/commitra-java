## What Is This?
Dev Environment Setup refers to the process of configuring a computer to write, test, and run software applications, in this case, Java programs. Setting up a development environment is like preparing a kitchen to cook a meal - you need the right tools, ingredients, and workspace to create a delicious dish. Just as a chef needs a well-organized kitchen with utensils, ingredients, and cooking appliances, a programmer needs a well-configured computer with the necessary software tools, libraries, and frameworks to write, test, and run their code.

## How It Works Internally
### Installing JDK 17 (LTS)
To start setting up a development environment for Java, you need to install the Java Development Kit (JDK) 17, which is the Long-Term Support (LTS) version. This is like installing a cooking appliance, such as an oven, that provides the necessary functionality to cook your meal. JDK 17 is the recommended version because it provides the latest features, security patches, and stability.

### JDK vs JRE vs JVM
The JDK, JRE, and JVM are three related but distinct concepts in Java development. The JDK is the Java Development Kit, which includes the JRE (Java Runtime Environment) and development tools like the compiler and debugger. The JRE is the Java Runtime Environment, which includes the JVM (Java Virtual Machine) and the Java Class Library. The JVM is the Java Virtual Machine, which executes Java bytecode on the underlying hardware. This is like having a kitchen with different areas, such as a cooking station, a dining area, and a storage room - each area has its own purpose and tools.

### IntelliJ IDEA
IntelliJ IDEA is a popular Integrated Development Environment (IDE) for Java development. It provides a comprehensive set of tools for writing, testing, and debugging Java code, including code completion, syntax highlighting, and project management. This is like having a well-organized kitchen with all the necessary utensils, ingredients, and cooking appliances.

### VS Code as Alternative
VS Code is another popular code editor that can be used for Java development. It provides a lightweight and flexible alternative to IntelliJ IDEA, with a wide range of extensions available for Java development. This is like having a smaller kitchen with a few essential utensils and appliances - it may not have all the features of a full kitchen, but it can still be used to cook a meal.

### Gradle
Gradle is a build tool that automates the process of compiling, testing, and packaging Java code. It provides a flexible and efficient way to manage dependencies, build artifacts, and deploy applications. This is like having a recipe book that provides step-by-step instructions for cooking a meal - it helps you manage the ingredients, cooking time, and presentation.

### Maven
Maven is another build tool that is widely used in Java development. It provides a standardized way to manage dependencies, build artifacts, and deploy applications. This is like having a different recipe book that provides a slightly different approach to cooking a meal - it may have its own set of ingredients, cooking techniques, and presentation styles.

### Git
Git is a version control system that helps you manage changes to your code over time. It provides a way to track changes, collaborate with others, and maintain a history of your code. This is like having a journal that records your cooking experiments, successes, and failures - it helps you learn from your mistakes and improve your cooking skills.

### GitHub
GitHub is a web-based platform that provides a centralized repository for Git version control. It provides a way to share your code with others, collaborate on projects, and maintain a public profile of your work. This is like having a cooking blog that showcases your recipes, cooking techniques, and culinary creations - it helps you share your passion for cooking with others.

### .gitignore
The .gitignore file is a configuration file that tells Git which files and directories to ignore in your project. It helps you avoid committing unnecessary files, such as build artifacts, temporary files, and configuration files. This is like having a filter that helps you select the right ingredients for your recipe - it helps you focus on the essential ingredients and avoid unnecessary ones.

### SSH Keys for GitHub
SSH keys are a way to securely authenticate with GitHub using a public-private key pair. It provides a way to establish a secure connection to your GitHub repository without using a password. This is like having a secure lockbox that protects your cooking secrets - it helps you keep your recipes and cooking techniques safe from unauthorized access.

### jshell
jshell is a Java shell that provides an interactive way to experiment with Java code. It allows you to write and execute Java code in a REPL (Read-Eval-Print Loop) environment, without the need to compile and run a separate Java program. This is like having a cooking playground where you can experiment with different ingredients, cooking techniques, and recipes - it helps you learn and improve your cooking skills in a fun and interactive way.

## Syntax and Structure
```text
# STEP 1: Install JDK 17 (LTS) on your computer
# STEP 2: Configure your IDE (IntelliJ IDEA or VS Code) to use the JDK
# STEP 3: Create a new Java project in your IDE
# STEP 4: Write your Java code in the project
# STEP 5: Compile and run your Java code using the IDE or command line
# STEP 6: Use Git to manage changes to your code over time
# STEP 7: Share your code with others using GitHub
In Phase 1, we will write this in real code.
```

## Practical Example
This section is intentionally omitted for Phase 0, as it requires runnable code that is not yet introduced.

## How This Connects to the Project
The Personal Computer Museum project requires a well-configured development environment to build and host the museum website. The development environment setup is like preparing a kitchen to cook a meal - you need the right tools, ingredients, and workspace to create a delicious dish. By setting up a development environment, you will be able to write, test, and run your Java code, which is essential for building the museum website. This matters to you because a well-configured development environment will help you avoid errors, reduce debugging time, and increase productivity.

## Common Mistakes Beginners Make
**Wrong idea:** Installing JRE instead of JDK.
**Correct idea:** JDK is required for development, while JRE is only needed for running Java programs.
Wrong idea: Not configuring the IDE to use the JDK.
Correct idea: The IDE needs to be configured to use the JDK to compile and run Java code.
Wrong idea: Not using Git to manage changes to code.
Correct idea: Git helps you track changes, collaborate with others, and maintain a history of your code.
Wrong idea: Not using SSH keys for GitHub authentication.
Correct idea: SSH keys provide a secure way to authenticate with GitHub without using a password.
Wrong idea: Not ignoring unnecessary files in the .gitignore file.
Correct idea: The .gitignore file helps you avoid committing unnecessary files, such as build artifacts and temporary files.

## Verification Tasks
## Verification Task 1
Your system shows an error message when trying to compile Java code. You have installed JDK 17 (LTS) and configured your IDE to use it. Diagnose and fix the issue.
## Solution 1
The issue is likely due to a missing dependency or a configuration error. Check the project dependencies and configuration files to ensure that everything is set up correctly.

## Verification Task 2
You are building a Java application and need to decide between using Gradle and Maven as the build tool. Defend your choice using the concepts learned in this topic.
## Solution 2
I would choose Gradle as the build tool because it provides a flexible and efficient way to manage dependencies, build artifacts, and deploy applications. Gradle also provides a more modern and streamlined approach to build automation compared to Maven.

## Verification Task 3
You are reviewing a Java code snippet and notice that it is missing a crucial configuration file. Find and fix the bug.
## Solution 3
The bug is likely due to a missing configuration file that is required for the application to run correctly. I would add the missing configuration file and update the code to use it.

## What Comes Next
The next topic is Growth Mindset for Engineering. This topic follows logically from Dev Environment Setup because having a well-configured development environment is essential for writing, testing, and running code, which is a critical aspect of software development. By setting up a development environment, you will be able to focus on writing code and learning new concepts, which is where the growth mindset comes in. One concrete concept from this topic that will reappear in Growth Mindset for Engineering is the importance of debugging and troubleshooting, which is a critical skill for software developers.

## Reference Summary
Dev Environment Setup is the process of configuring a computer to write, test, and run software applications. It involves installing the JDK, configuring the IDE, creating a new Java project, writing Java code, compiling and running the code, using Git to manage changes, and sharing code with others using GitHub. The most common production mistake is not configuring the IDE to use the JDK, which can lead to compilation errors. This concept connects to the Personal Computer Museum project because a well-configured development environment is essential for building and hosting the museum website. By understanding how to set up a development environment, you will be able to write, test, and run Java code, which is critical for building the website. This enables you to focus on writing code and learning new concepts, which is where the growth mindset comes in. CORE INSIGHT: A well-configured development environment is essential for writing, testing, and running software applications.