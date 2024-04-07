[toc]
# SFT Guidelines 

| **Principle/Aspect** | **Guidelines** |
|----------------------|----------------|
| **Accuracy** | - No errors in code or grammar.<br>- No logical errors.<br>- Use the most optimal approaches.|
| **Helpfulness** | - Accurately reflect user's intent.<br>- Address the user's query fully.<br>- Provide relevant additional information. |
| **Ease of Understanding** | - Use plain language.<br>- Responses should be easy to read.<br>- Leverage bullet points or lists for clarity.<br>- Assume the user has basic prerequisite knowledge but is new to the specific topic. |
| **Precision** | - Responses should be concise and to the point.<br>- Avoid unnecessary elaboration. |
| **Format Guidelines** | - Use Markdown format for responses.<br>- Inline code in single backticks, code blocks in triple backticks with language specified.<br>- Equations in LaTeX format. |
| **Response Structure** | - Begin with interpreting the user's query and identifying relevant concepts.<br>- Correct any incorrect information in the user query.<br>- Be flexible to best answer the user query. |
| **Code Guidelines** | - Code must be complete and functional.<br>- Enclose code in functions where appropriate.<br>- Include example usage of code.<br>- Comments should add value and provide clarity.<br>- Clearly state and include necessary dependencies. |
* * *
## Format Guidelines
[Cheat sheet for Google Colab](https://colab.research.google.com/github/Tanu-N-Prabhu/Python/blob/master/Cheat_sheet_for_Google_Colab.ipynb)
1. **Markdown Formatting**:
   - Inline code should be wrapped in single backticks (\`).
   - Code blocks should be wrapped in triple backticks (\`\`\`) and specify the programming language for syntax highlighting.
     ```
	 ```python
     print("hello")
     ```
	 ```
2. **Equations**: All equations must be in LaTeX format.

## Response Guidelines
### 1. Beginning the Response

#### Acknowledgement and Interpretation
- Start by **acknowledging** or **interpreting** the user's query.
- **Identify** any relevant **concepts** and provide explanations.

#### Uncertainty and Correction
- If the intent of the user's query is uncertain, make an effort to interpret it and provide helpful answers.
- Correct any incorrect information provided by the user with your best effort.

| ✅ **Correct Approach** | ❌ **Incorrect Approach** |
|------------------------|--------------------------|
| **User:** Implement a function in Python that counts the number of set bits (1s) in the binary representation of a given integer. | **User:** Implement a function in python that counts the number of set bits (1s) in the binary representation of a given integer. |
|**Identified the concept used to solve the problem; and added a longer explanation because the user's query did not original include the name of the concept (algorithm)** <br><br>**Assistant:** You can count the number of set bits (1s) in the binary representation of an integer using Brian Kernighan's Algorithm. This algorithm works by repeatedly flipping the least significant set bit of the number to 0 and counting how many times this operation is done until the number becomes 0. The algorithm takes advantage of the fact that subtracting 1 from a number flips all the bits after the least significant set bit. Here's how you can implement it in Python: `{code}` | **Did not interpret the query or identify any concepts used in the code**<br><br>**Assistant:** Sure! `{code}`... |
| **User:** I want to move all .py files from a directory to another. Remember, my source directory has a nested structure, which I want to preserve in the destination directory. Write python script for this. | **User:** I want to move all .py files from a directory to another. Remember, my source directory has a nested structure, which I want to preserve in the destination directory. Write python script for this. |
| **Interpreted the query with multiple conditions (move directory + nested + preserve destination) in a concise manner.**<br><br>**Assistant:** Sure, I can help you move all .py files from one directory to another while preserving the nested directory structure. | **Jumped strained into code without any Beginning**<br><br>**Assistant:****Assistant:** Sure. This is how it is implemented: `{code}` |
| **User:** Print I love coding in C | **User:** Print I love coding in C |
| **Direct reply for a short query**<br><br>**Assistant:** To print "I love coding in C" in a C program, you would use the printf function. Here is a simple example: `{code}` |**Over-explaining for a simple request**<br><br> **Assistant:** To begin writing a program in the C programming language that outputs the phrase "I love coding in C" to the console, one must first understand the fundamental structure and syntax of a C program... |

#### Key Takeaways
- **Understand the intent of the prompt** 
- **Interpretation**: Clearly acknowledge the user's request or question before proceeding.
- **Concept Identification**: Identify and explain key concepts or methods that will be used to address the query.
- **Avoid Over-Simplification**: Provide an explanation that educates the user without assuming prior knowledge.
- **Avoid Over-Complexity**: Do not over-explain with unnecessary context for simple requests.

### 2. Code Explanation

#### Types of Explanations
- **Brief Overview**: Provide a high-level overview of the approach before the code without diving into individual steps.
- **Detailed Description**: Offer a more detailed explanation after the code, possibly referencing specific lines, functions, and variables.

#### Importance of Context
- Understand the **intent of the query** and **user's knowledge level** to tailor the explanation appropriately.

| ✅ **Correct Approach** | ❌ **Incorrect Approach** |
|------------------------|--------------------------|
| **User:** I want to move all .py files from a directory to another, preserving the nested structure. | **User:** I want to move all .py files from a directory to another, preserving the nested structure. |
| **Assistant:** The overall approach involves recursively searching through all the python files to determine their corresponding source and destination paths. Here is how it is implemented in Python: `{code}` | **Assistant:** Here is the code below: `{code}` (No explanation provided on the method used.) |
| **User:** Tell me how can I use `range()` to print numbers from 10 to 1. | **User:** Tell me how can I use `range()` to print numbers from 10 to 1. |
| **Assistant:** You can use the `range()` function in Python to generate numbers from 10 to 1 in reverse order by specifying the start, stop, and step parameters. In this case, you start at 10, stop before 1 (since the stop is exclusive), and use a step of -1 to count backwards. Here's how you can do it: `{code}` | **Assistant:** Sure, the `range` function in Python can be used to return a list by wrapping the `range` function in a list(). `{code}` (No explanation on how the code works.) |
| **User:** Add comments to this code `def hellow(p): print(p)` | **User:** (Same as left) |
| **Assistant:** Certainly! Below is your Python function with comments added for clarity. Comments in Python start with a `#` and are used to explain what specific parts of the code do. `{code}` | (No corresponding incorrect approach for adding comments.) |
| **User:** I am using a PostgreSQL database for my project. It has a critical table named `employees`. I need a python snippet utilizing the `psycopg2` library to establish a connection to the database and interact with the `employees` table. | **User:** (Same as left) |
| **Assistant:** Below is a basic Python snippet that establishes a connection to a PostgreSQL database and demonstrates how to insert a new row, update an existing row, retrieve data, and delete a row from the `employees` table. `{code}` 1. Connection Establishment: `psycopg2.connect()` is used to establish a connection with your PostgreSQL database using the provided credentials. 2. Cursor Creation: A cursor is created using `conn.cursor()`. This cursor is then used to execute SQL commands. ... [Detailed Code Explanation] |  |

#### Best Practices
- **Match the Explanation to User's Level**: Tailor the complexity of your explanation to the user's understanding and the query's complexity.
- **Clarify Before Code**: Offer a brief overview of the approach before diving into the code to set context.
- **Detail After Code**: After presenting the code, delve into a detailed explanation if the code's steps are complex or numerous.

### 3. Code Summary
When a query requires an understanding of the code's functionality rather than the code itself, a summary of the code can be provided. This summary should concisely explain the logic or the approach of the code, focusing on the key functionalities **without** diving into the specifics of the **implementation**.

 Example : 
| ✅Correct                                                                                                                                                                                                                                                                                                       | ❌Incorrect                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User:** Can you explain how a basic weather app retrieves and displays the current weather for a user's location?<br>**Assistant:** Sure, a basic weather app works in four main steps:<br>1. **Determine Location:** *Add summary*<br>2. **Fetch Weather:** *Add summary*<br>3. **Process Data:** *Add summary*<br>4. **Show Weather:** *Add summary* | **User:** Can you explain how a basic weather app retrieves and displays the current weather for a user's location?<br>**Assistant:** Sure, a basic weather app works in four main steps:<br>1. **Determine Location:**<br>2. **Fetch Weather:**<br>3. **Process Data:**<br>4. **Show Weather:**<br>Here is an example of a weather app written in javascript that displays the current weather for a user's location:<br>```// Code for the mentioned app ```|

#### Key Points for Code Summary:
- **Focus on Logic**: Concentrate on explaining the logic or the approach behind the code.
- **Be Concise**: Keep the summary brief but informative enough to convey the essential functionality.
- **Avoid Technical Jargon**: Use plain language to make the summary accessible to users with varying levels of technical expertise.

### 4. Code Debugging
When addressing a code correction or debugging query, it's crucial to first identify and clearly explain the incorrect issue within the code. After pinpointing the problem, provide a detailed explanation of the correct code and the necessary adjustments, ensuring that the user understands both what was wrong and how it was fixed.

#### Key Steps for Code Debugging:
1. **Identify the Issue**: Clearly state the problem within the code, explaining why it's incorrect or causing an issue.
2. **Explain the Solution**: Offer a corrected version of the code and thoroughly explain why this adjustment solves the problem.
3. **Educate on Best Practices**: Where applicable, provide insights into best practices that can prevent similar issues in the future.

Examples

✅ **Correct Approach**

**User:** Hey, when I run my code I get wrong output. Can you help me fix it please ?
```python
def add_numbers(num1, num2):
    total = num1 + num2
    return total
num1 = input("Insert number 1: ")
num2 = input("Insert number 2: ")
print(f"The sum of the given number is: {add_numbers(num1,num2)}")
```

**Assistant:** 
Sure, I can help you fix your code. The issue with your code arises from the `input()` function, which returns data in string format. This results in your `num1` and `num2` variables being strings, so the `+` operator will concatenate (merge) the strings rather than calculating the sum of the numbers.
To rectify this issue, you need to convert the string inputs to numeric values before performing the addition. This conversion can be done using the `int()` function for integers or the `float()` function for decimal numbers. Here's the corrected version of your code with integer conversion:
```python
def add_numbers(num1, num2):
    total = num1 + num2
    return total

# Convert input to integers
num1 = int(input("Insert number 1: "))
num2 = int(input("Insert number 2: "))

print(f"The sum of the given number is: {add_numbers(num1, num2)}")
```

To avoid similar issues in the future, focus on two key areas:

- **Input Validation**: Always validate user inputs to ensure they match the expected format and type. This is crucial for operations that depend on numerical inputs, where ensuring the data is in the correct numerical format prevents common errors.

- **Error Handling**: Implement robust error handling using `try` and `except` blocks. This approach allows your program to gracefully handle unexpected inputs or errors, improving its resilience and reliability.

❌ **Incorrect Approach**

**User:** (Same as above)

**Asssitant:**

Sure, here is the fixed code : 

```python
def add_numbers(num1, num2):
    total = num1 + num2
    return total

# Convert input to integers
num1 = int(input("Insert number 1: "))
num2 = int(input("Insert number 2: "))

print(f"The sum of the given number is: {add_numbers(num1, num2)}")
```

#### Best Practices for Writing Summaries and Debugging
- **Understand the User's Perspective**: Tailor your explanation to the user's level of understanding, avoiding overly technical language if not appropriate.
- **Encourage Learning**: Use the code summary and debugging process as an opportunity to educate the user, promoting better coding practices.
- **Be Clear and Direct**: Clearly distinguish between what was wrong and how it was corrected, especially in debugging scenarios, to enhance the user's understanding.

### 5. Closing Remarks Guidelines

In your closing remarks, aim to add value to your response by including considerations or reminders that might be relevant to the user's context. This can help ensure that the solution provided is not only technically correct but also practically useful.

#### Elements to Include in Closing Remarks:

1. **Major Assumptions**: If your response is based on certain assumptions (e.g., the user has read and write permissions), list these explicitly to avoid confusion.
2. **Variable Updates**: Remind users to update any variables specific to their environment (e.g., file paths, database credentials) to avoid common pitfalls.
3. **Runtime Complexity**: All algorithmic solutions must include the runtime complexity.
4. **Risks and Vulnerabilities**: Highlight any potential risks or vulnerabilities associated with the provided solution and suggest ways to mitigate them.
5. **Optimization Directions**: If applicable, suggest directions for further optimization to encourage users to think about improvements.
6. **Error Handling and Testing**: Advise on error handling practices and the importance of testing the solution, especially in a production environment.
7. **Additional Details**: Include any other details that might be relevant to the user's query or the provided solution.

#### Example of Correct vs. Incorrect Closing Remarks

| ✅ **Correct Approach** | ❌ **Incorrect Approach** |
|------------------------|--------------------------|
| **User Query**: Request for a Python snippet to interact with a PostgreSQL database. | **User Query**: Same as the correct approach. |
| **Assistant's Closing Remark**: Before running, remember to replace the database credentials and connection details. Ensure to handle exceptions that might occur during database operations, such as connection errors or SQL errors, to make your application more robust. | **Assistant's Closing Remark**: Done! This script uses the psycopg2 library to establish a connection to the database for you to interact with. (No mention of updating credentials or error handling.) |
| **User Query**: Print "I love coding in C". | **User Query**: (Same) |
| **Assistant's Closing Remark**: Remember to consider the context of your C program and adjust the printf function's usage as necessary for your specific needs. | **Assistant's Closing Remark**: Keep in mind, this simple example of printing a message in C is just the beginning. It's important to consider how similar concepts can be expanded or optimized for more complex applications. (Irrelevant for a simple print statement.) |

#### Best Practices for Closing Remarks
- **Be Relevant**: Ensure that your closing remarks are directly relevant to the user's query and the provided solution.
- **Encourage Best Practices**: Use closing remarks as an opportunity to guide users towards best practices in coding, testing, and deployment.
- **Avoid Overloading Information**: While it's important to be thorough, avoid adding unnecessary or overly detailed information that might overwhelm the user.
# Code Guidelines

Ensuring that the code provided in responses is complete and ready to use is essential for user satisfaction and understanding. The guidelines below outline the expectations for code completeness in responses.

## 1. Complete Code

When providing code in a response, it's important to ensure that the code is:

- **Fully Functional**: The code should be ready to run without requiring additional modifications or completions by the user. It should not contain placeholders like "TODO" that imply unfinished work.
- **Not Pseudocode**: Pseudocode is useful for explaining algorithms conceptually but should not replace actual code in responses. Users expect executable code snippets that they can directly use or adapt to their needs.
- **Self-contained**: If possible, the code should not rely on external dependencies or resources that aren't explicitly mentioned or provided in the response. If external dependencies are necessary, instructions for their installation and use should be included.

#### Best Practices for Providing Code

- **Ensure Completeness**: Before including a code snippet in your response, verify that it includes all necessary components to function as expected.
- **Test the Code**: Whenever possible, test the code to ensure it works correctly and produces the expected results.
- **Include Usage Examples**: Providing a simple usage example can greatly enhance the user's understanding and ability to apply the code to their own context.

## 2. Code Function Guidelines

When providing code in responses, consider how it is structured, particularly whether to encapsulate the logic within a function.

### Encapsulation in Functions

- **When to Use Functions**: Generally, code should be encapsulated within functions to enhance reusability, readability, and organization. This is especially important for multi-step processes or when the code performs a specific, coherent task.
- **Exceptions**: For extremely simple code snippets that consist of a single line or merely call a built-in function, encapsulation in a function may not be necessary.

Examples
✅ **Correct Approach**

**(Encapsulated in function with two features)**
**User:** Can you write a python code to calculate area of circle in python ?
**Assistant:** 
(make sure to follow all other instructions mentioned above to give the explanation)
```python
def calculate_and_print_area(radius):
    area = 3.14 * radius ** 2
    print(f"The area of the circle is {area}")

# Example usage:
calculate_and_print_area(5)
```
✅ **Correct Approach**

**(Simple built-in function call, no additional logic)**
**User:** Write the Python code to print the sorted list [2, 5, 4, 1, 6, 3].
**Assistant:** 
(make sure to follow all other instructions mentioned above to give the explanation)
```python
unsorted_list = [2,5,4,1,6,3]
sorted_list = sorted(unsorted_list)
print(sorted_list)
```

### Best Practices for Function Encapsulation

- **Clear Purpose**: Each function should have a clear, singular purpose, making the code easier to understand and test.
- **Naming Conventions**: Use descriptive names for functions that clearly indicate what the function does.
- **Parameters and Return Values**: Design functions to accept parameters for their inputs and use return values to output their results, rather than relying on global variables or printing directly within the function (unless printing is the function's purpose).
- **Documentation**: [Read the Docstrings section](#4-docstrings)

Note

Encapsulating code in functions not only makes your code more organized and reusable but also helps in isolating different parts of the code, making debugging and testing easier.

## 3. Code Testing

If the code wrapped in a function, always include at least 1 example of running
the code with print statements at the end after the comment `# Example Usage` .
**Do not  include the expected output.**
✅ **Correct Approach**

```python
def linear_search_with_count(lst, target):
    """Perform a linear search for the target in the list lst."""
    comparisons = 0
    for i, element in enumerate(lst):
        comparisons += 1
        if element == target:
            return i, comparisons
    return -1, comparisons

# Example usage
lst = [5, 3, 7, 1, 9, 8]
target = 7
index, comparisons = linear_search_with_count(lst, target)
print(f"Index of target ({target}): {index}, Comparisons made: {comparisons}")

```
## 4. Docstrings: 

1. Do **NOT** add docstrings by default.
    1. You **CAN** add a docstring for the **function description** if the purpose of the function is not clear.
2. Do **NOT** include explanations for:
    1. Parameters.
    2. Return type.
    3. Other variables inside the function.

## 5. Code Comments Guidelines
[Useful and Useless Code Comments](https://blog.jim-nielsen.com/2021/useful-and-usless-code-comments/)
### Format
Proper formatting of comments is crucial for maintaining readability and understanding of code. Follow these formatting guidelines for comments:

- **Space After Comment Symbol**: Always include a space after the comment symbol (e.g., `#` in Python, `//` in JavaScript) before starting your comment text.
- **Placement**: Comments can be placed either on the same line as the code, following two spaces after the code, or on a separate line directly above the code they refer to, maintaining the same level of indentation as the code.
- **Capitalization**: The first word of a comment should be capitalized, unless it starts with an identifier that begins with a lower case letter. **Do not alter the case of identifiers within comments**.

#### Value-Adding Comments
Not all comments are equally useful. To ensure comments add value to the code:

- **Clarify Meaning**: Comments should add precision to the code by clarifying the meaning of complex lines or blocks of code that might not be immediately clear to another reader.
- **Provide Intuition**: Good comments can offer insight into the reasoning behind a piece of code, representing a simpler or more abstract way of thinking about what the code does.
- **Avoid Redundancy**: If a line of code is straightforward and can be easily understood without additional explanation, adding a comment may be unnecessary.

### Deciding When to Comment
- **Add Comments for Complex Logic**: If a piece of code involves complex logic or is not immediately intuitive, a well-placed comment can greatly aid in understanding.
- **Skip Comments for Self-Explanatory Code**: For code that is clear and simple, refrain from adding comments to avoid cluttering the codebase with redundant information.

✅ **Correct** - Provided intuition towards what the most important line of code in the function means and how it contributes to what the function does.

```python
def count_set_bits(n):
  """Counts the number of set bits (1s) in the binary representation of the given integer."""
  count = 0
  while n:
    # Flip the least significant set bit
    n &= (n - 1) 
    count += 1
  return count
```
❌ **Wrong** -  
- Most of the comments do not add extra value;
-  `count = 0` , `while n` , `count += 1` are selfexplanatory.
- The first letter of the comment starts with a small case, which is incorrect.   

```python
def count_set_bits(n):
    """
    Counts the number of set bits (1s) in the binary representation of the
    given integer.
    """
    count = 0  # first, set count as zero
    while n:  # while n is true
        n &= (n - 1)  # Flip the least significant set bit
        count += 1  # add one to count after flipping the least significant set bit
    return count
```
## 6. Dependencies

Always ensure to install and import all necessary dependencies for your project to function properly.

✅ Correct Usage

**User**: How to read CSV in Python?

**Assistant**: The pandas library is one of the most popular Python libraries for data analysis. Let's use the `read_csv` function in the pandas library to read a CSV in Python. First, install the pandas library in your environment:
```
```bash
pip3 install pandas
```

To read a CSV file with pandas, use the following code:
```
```python
import pandas as pd

# Replace with your csv filepath
file_path = 'your_csv_file.csv'

def read_csv(file):
    return pd.read_csv(file)
	
read_csv(file_path)
```

#### Imports Guidelines

When importing packages and modules in Python, follow these best practices:

- Use `import x` for importing packages and modules.
- Use `from x import y` where `x` is the package prefix and `y` is the module name with no prefix.
- Use `from x import y as z` under any of the following circumstances:
  - Two modules named `y` are to be imported.
  - `y` conflicts with a top-level name defined in the current module.
  - `y` conflicts with a common parameter name that is part of the public API (e.g., features).
  - `y` is an inconveniently long name.
  - `y` is too generic in the context of your code (e.g., `from storage.file_system import options as fs_options`).
- Use `import y as z` only when `z` is a standard abbreviation (e.g., `import numpy as np`).
 
# Sample notebooks : 
## ❌ Wrong
1. [Notebook1](https://colab.research.google.com/drive/192VwnHKwvgIRz2_DPOX5lvPLU9HhO1KP#revisionId=0B_2XFLV2hMm7d1k3ZHJwTUZSUFhyeUYvRHM2allmSjB4Z3Q4PQ) 
	1. The first question is not a coding question.
	2. The first question is not related to algorithms
	3. The mathematical proof is extra detail which is not required.
2. [Notebook2](https://colab.research.google.com/drive/14eEfQL5Ngh1F8Mz3ETxb9hQBcfXJQjFM#revisionId=0B_2XFLV2hMm7VlRHUFZSNUszQVRmQnNadnRxZXdvaVpaWTg4PQ)
	1.The assistant's response does not seem customized to user's query   
	 >User's intent 
			>1. refactor python script to add type hints
			>2. what benefits does this provide for maintainability and error prevention ?

	2. The assistant's response starts with `Definitely!` which does not sound natural when replying to the  user's query. Also the response format does not match as described before 
	3. This statement is incorrect 
	  `a function takes a list of integers and returns a dictionary of strings and floats like this`
	  
		  1. The function has output type of `Dict[str, int]`
		  2. From the inline comment in the function and example usage we see even the input type is incorrect. It should be `word_list: List[str]`

	4. No mention about refactoring the code. 
## ✅ Correct
1. [Notebook1](https://colab.research.google.com/drive/192VwnHKwvgIRz2_DPOX5lvPLU9HhO1KP#revisionId=0B_2XFLV2hMm7OWhSbjhEMEt1QlA3eHdLUjNqWUgzUFpNM1JzPQ)
	1. Fixed the following issues 
	 >1. The first question is not a coding question.
	>	2. The first question is not related to algorithms
	>3. The mathematical proof is extra detail which is not required.
# Checklist 
 
 - [ ] **Prompt Check**
	  - [ ] Confirm the prompt is a coding question.
	  - [ ] Ensure that the first question is directly related to the type of metadata.

- [ ] **Response Check**
  - [ ] Verify the answer accurately and completely addresses the question.
  - [ ] Confirm that the code is the best implementation.
  - [ ] Check for any specific requirements in the question that were missed.
  - [ ] Ensure the output format is similar to what is described in the guidelines.

- [ ] **Testing Check**
  - [ ] Test code extensively on selected test cases, including but not limited to: empty lists/strings, whitespaces, negative numbers, repeating elements, missing elements, very small/large values, single characters, zero divisions, corner cases, invalid operations, non-connected graphs, wrong types, even/odd number of elements.
  - [ ] Paste all test cases in the comment section, not in the notebook.
  - [ ] Conduct repeat testing after any code modification.
  - [ ] Add one-two example usage in the conversation.

- [ ] **Comments Check**
  - [ ] Remove docstrings, Only use docstrings if explicitly asked.
  - [ ] Use comments effectively to offer insights not immediately obvious (Only on the code lines that are harder to grasp).
  - [ ] Avoid redundant or overly verbose comments.
  - [ ] Remove references to non-existent elements (e.g., ‘fixed part’).

- [ ] **Headers Check**
  - [ ] Ensure each cell is properly attributed to either **Assistant**, **User**, or # Assistant.

- [ ] **Text Check**
  - [ ] Confirm markdowns contain correct, unambiguous, concise information, well-explained, and grammatically correct.
  - [ ] Avoid ‘empty’ cells that don’t provide useful information.
  - [ ] Use code blocks for code snippets and single backticks for inline code and variables.
  - [ ] Use LaTeX for equations.
  - [ ] Maintain a professional, educational, friendly, and proactive tone.
