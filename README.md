# VNM Interpreter – Part 4: Evaluation

A Java-based interpreter developed as part of **CPS 710 – Compiler Design** at Toronto Metropolitan University. This project focuses on implementing the evaluation stage of the VNM programming language by traversing Abstract Syntax Trees (ASTs) and executing language constructs using the Visitor design pattern.

## Project Overview

The VNM Interpreter processes statements written in the VNM programming language through lexical analysis, syntax analysis, Abstract Syntax Tree construction, and evaluation.
Part 4 focuses on the final stage of this process: **evaluation**. It extends the parsing and AST construction functionality established in earlier project stages by introducing an evaluator that visits syntax tree nodes and executes the corresponding operations.
The project covers arithmetic expression evaluation, Boolean comparisons, conditional statements, and output operations. It demonstrates how a programming language interpreter transforms structured syntax representations into executable behaviour.

## Key Features

- **Abstract Syntax Tree Evaluation:** Traverses AST nodes to evaluate supported VNM expressions and statements.
- **Visitor Design Pattern:** Organizes evaluation logic into node-specific visitor methods, separating interpreter operations from AST structure.
- **Literal Evaluation:** Processes integer, string, and Boolean literals.
- **Arithmetic Operations:** Supports addition, subtraction, multiplication, and division with Java-style operator precedence and associativity.
- **Boolean Comparisons:** Evaluates comparison expressions involving numeric values.
- **Conditional Execution:** Supports `if`, `elif`, and `else` statements, executing only the first branch with a true condition.
- **Output Operations:** Supports `print` and `println` statements for integer, Boolean, and string arguments.
- **Automated Testing:** Includes predefined test cases and command-line scripts for evaluating interpreter functionality.

## Technical Architecture

The interpreter follows a structured language-processing pipeline consisting of lexical analysis, syntax analysis, AST construction, and evaluation.

### Lexical and Syntax Analysis

The lexical analyzer identifies tokens representing language elements such as literals, operators, and keywords. The parser processes these tokens according to the VNM grammar and constructs a structured representation of the input.

### Abstract Syntax Tree Construction

Parsed expressions and statements are represented using Abstract Syntax Trees. Each node corresponds to a specific language construct, allowing the interpreter to process expressions and statements according to their syntactic structure.

### AST Evaluation

The evaluation stage uses the **Visitor design pattern** to traverse AST nodes and execute supported operations. Visitor methods evaluate arithmetic expressions, Boolean comparisons, conditional statements, and output instructions.
The primary evaluation logic is located in `VNMEval.java`, which contains node-specific visitor methods responsible for interpreting the syntax tree.

## Supported Language Operations

### 1. Literal Evaluation

The evaluator handles three fundamental literal types:

- Integer literals
- String literals
- Boolean literals

### 2. Arithmetic Expressions

The interpreter supports integer addition, subtraction, multiplication, and division. Arithmetic expressions follow Java-style operator precedence and associativity.

Example: -3 + 5 - 10 - 2;
Expected Result: -10

### 3. Boolean Comparisons

The evaluator processes Boolean literals and comparison operations involving numeric values. These expressions produce Boolean results that can be used in conditional statements.

Example: 3 <= 6
Expected Result: true

### 4. Conditional Statements

The interpreter supports conditional execution using `if`, `elif`, and `else` statements. Conditions are evaluated sequentially, and only the first satisfied branch is executed. If none of the preceding conditions evaluates to true, the `else` branch is executed when present.

Example: 
if 2 > 5 then
    println "Hello";
elif #1 then
    println "World";
else
    println "abc123";
fi;

Expected Output: World

### 5. Output Operations

The interpreter supports two output statements:

- **`print`:** Displays evaluated values.
- **`println`:** Displays evaluated values followed by a newline.

Both operations are designed to handle integer, Boolean, and string arguments.

## Project Structure

The repository is organized into the following primary directories and files:

- **`AST/`** – Contains Abstract Syntax Tree node classes used to represent parsed language constructs.
- **`Tests/`** – Contains predefined test inputs and corresponding expected outputs.
- **`src/`** – Contains supporting Java source files, token classes, and testing components.
- **`use_provided/`** – Contains course-provided reference files for the VNM grammar and evaluator.
- **`use_your_own/`** – Contains supporting files for generating a custom evaluator.
- **`VNM.jjt`** – Defines the VNM grammar and AST construction rules.
- **`VNM.java`** – Contains the generated parser for processing VNM statements.
- **`VNMEval.java`** – Implements visitor methods for AST evaluation and statement execution.
- **`TestVNM.java`** – Provides the interface for testing VNM statements.
- **`Token.java`** – Defines the token representation used during lexical and syntax analysis.
- **`makefile`** – Automates compilation and build operations.
- **`run`** – Executes the interpreter for interactive testing.
- **`runtests`** – Executes predefined test cases for interpreter validation.

## Technologies Used

- **Java:** Primary programming language for interpreter implementation.
- **JavaCC:** Used for lexical analysis and parser generation.
- **JJTree:** Used to generate Abstract Syntax Trees.
- **Visitor Design Pattern:** Supports AST traversal and evaluation.
- **GNU Make:** Automates project compilation and build operations.
- **Shell Scripts:** Support interpreter execution and automated testing.
- **Git and GitHub:** Used for version control and source-code management.

## Build and Execution

### Prerequisites

The project requires:

- Java Development Kit (JDK)
- JavaCC and JJTree
- GNU Make
- Unix-compatible shell environment

### 1. Compile the Project

Navigate to the project root directory and execute: make
To force recompilation when necessary: make -B

### 2. Run the Interpreter

Execute the provided script: ./run
The interpreter can then process supported VNM statements entered through the command-line interface.

### 3. Run Automated Tests

Execute the predefined test suite:
./runtests

The testing script processes predefined VNM inputs and compares the generated results against their corresponding expected outputs.

## Testing and Validation

The repository includes test cases covering the principal evaluation requirements of Part 4.

- **Boolean Evaluation:** Tests the processing and evaluation of Boolean literals.
- **Arithmetic Operations:** Tests integer arithmetic expressions, including addition, subtraction, multiplication, and division.
- **Comparisons:** Tests numeric comparison expressions and their corresponding Boolean results.
- **Conditional Statements:** Tests `if`, `elif`, and `else` execution to verify conditional branch selection.
- **Output Operations:** Tests the printing of evaluated integer, Boolean, and string values.

Test cases are organized in the `Tests/` directory, with `.in` files containing test inputs and `.expected` files specifying the expected outputs. The project provides both interactive execution and automated testing to support validation and debugging.

## Learning Outcomes

This project provides practical experience in compiler and interpreter development, particularly in implementing the evaluation stage of a programming language.

Key concepts explored include:

- Abstract Syntax Tree construction and traversal
- Visitor-based interpreter architecture
- Arithmetic expression evaluation
- Operator precedence and associativity
- Boolean expression processing
- Conditional control flow
- Java-based language processing
- Build automation and command-line testing

## Project Information

- **Course:** CPS 710 – Compiler Design
- **Institution:** Toronto Metropolitan University
- **Project:** VNM Interpreter – Part IV: Evaluation
- **Primary Programming Language:** Java

## Acknowledgments

This project was developed as part of the CPS 710 academic coursework at Toronto Metropolitan University. The repository includes course-provided materials and reference components supporting the implementation of the VNM interpreter. 
