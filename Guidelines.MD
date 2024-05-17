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

## Updates/changes

1. [**Use of external files in code**](#external-files-in-code) : If you reference any external files in your code, the code should be wrapped up in a function, and it should be called with a dummy filename in a SEPERATE CELL 
2. [**Latex syntax**](#latex-syntax) : Use \\\\(..\\\\) , or \\\\[...\\\\] to define latex code instead of using \$..\$ or $$..$$
3. [**Install commands**](#6-dependencies) : All install commands must precede the code where they are used in. 
4. [**Code explanation start**](#overview-and-code-presentation): Any content before the actual code should be minimized. At most 4 sentences can be present before starting the code. 
5. [**Post code explanation**](#post-code-explanation) :  Adjust the complexity of this explanation based on how the user query is interpreted. 

## Format Guidelines
[Cheat sheet for Google Colab](https://colab.research.google.com/github/Tanu-N-Prabhu/Python/blob/master/Cheat_sheet_for_Google_Colab.ipynb)
### Markdown Formatting:
   - Inline code should be wrapped in single backticks (\`).
   - Code blocks should be wrapped in triple backticks (\`\`\`) and specify the programming language for syntax highlighting.
     ```
	 ```python
     print("hello")
     ```
	 ```
### Equations: All equations must be in LaTeX format.

### Latex syntax : 
1. Use \\\\(..\\\\) , or \\\\[...\\\\] to define latex code instead of using \$..\$ or $$..$$
2. [mathjax](https://docs.mathjax.org/en/latest/input/tex/macros/index.html)


## Response Guidelines
### Beginning the Response

#### Overview and Code Presentation
- **Brief Overview**: Set the context without overwhelming the user. Provide a concise overview of the approach in **no more than four sentences** before presenting the code. Judge the level of detail based on the user prompt. 
	- Slightly higher detail if the prompt is indirect . 
	- Very less if the user query is very specific, and asking for the code/function. 
- **Code**: Immediately present the code block after your brief overview, ensuring it addresses the user's request directly.

#### Post-Code Explanation

Offer an explanation after the code, adjusting the depth based on the complexity and clarity of the prompt and code. Use references to specific lines, functions, and variables **if needed**, but keep it succinct if the code is straightforward.
#### Acknowledgement and Interpretation
- Start by **acknowledging** the user's query, ensuring there's clarity on what's being asked.
- **Identify** any key **concepts** involved and give a succinct explanation if necessary.

#### Uncertainty and Correction
- If the query's intent is unclear, attempt to interpret it and provide a constructive response.
- Correct any misinformation in the user's query with tact and accuracy.

#### Key Takeaways
- **Understand the Prompt**: Grasp the intent behind the user's request before responding.
- **Interpretation**: Begin your response by clearly acknowledging the query.
- **Concept Identification**: Briefly explain relevant concepts or methods to be used.
- **Balance**: Avoid oversimplifying for complex queries or overcomplicating simple ones.



### Code Debugging
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
```
```python
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

### External files in code
1. If you reference any external files in your code, the code should be wrapped up in a function, and it should be called with a dummy filename in a SEPERATE CELL (Code cell or markdown cell does not matter) 
##### Example : 
---
**Assistant**
```python
def read_csv_and_count(file):
    df = pd.read_csv(file)
    return df['test'].count()
```

**Assistant**
```python
read_csv_and_count('file.csv')
```
---
##### Example : 

---
**User**
Can you give python code to take filename and print filename without extension ?

[OLD]
**Assistant**
Sure, you can use the `pathlib` module to print a filename without the extension. Here is how you can do it.
```python
from pathlib import Path
filename = "sample.json"
print (Path(filename).stem)
```
The `Path.stem` attribute from the pathlib library in Python gives you the filename without its extension.


[NEW]
**Assistant**
Sure, you can use the `pathlib` module to print a filename without the extension. Here is how you can do it.
```python
from pathlib import Path
def get_filename_without_extension(path):
    return Path(path).stem
```
```python
# Example usage:
filename = get_filename_without_extension("sample.json")
print(filename)
```
The `Path.stem` attribute from the pathlib library in Python gives you the filename without its extension.

---
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
```
```python
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
- **Placement**: Comments can be placed following two spaces after the code, or on a separate line directly above the code they refer to, maintaining the same level of indentation as the code.
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

1. Always ensure to install and import all necessary dependencies for your project to function properly.
2. Install commands should always precede their usage in the code. 


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

def read_csv(file):
    return pd.read_csv(file)
```
```python

# Replace with your csv filepath
file_path = 'your_csv_file.csv'
read_csv(file_path)
```

#### Import Guidelines

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
 
# Avoid These Issues in Your Conversations

- **Code Related Issues**
	- [ ] The code is incorrect
	- [ ] Test cases are not provided in the comment section for complex algorithms or No ‘Example usage’
	- [ ] The code is not readable
	- [ ] Output format is not the desired one
	- [ ] The code provided in the coding cell cannot run
	- [ ] Test examples outcomes are commented
	- [ ] Non-trivial code is not embedded in the function
	- [ ] Missing comments for complex issues
	- [ ]  Comments are in the same line as the coding line
	- [ ]  Non-consistent 4-spaces/tab indentation for Python tasks
	- [ ]  External files are called in the same code block.
	- [ ]  Using both single and double quotes within the same notebook
	- [ ]  
- **Completeness Related Issues**
  - [ ] The assistant’s content is correct but does not answer the user’s question
  - [ ] The assistant does not completely answer the user’s questions 
  - [ ] The assistant provides non optimal code in the first turn and subsequently provides optimal code when prompted by the user. 
  - [ ] Lack of install commands for external libraries. 
  - [ ] Non-stated assumptions by the assistant
  - [ ] Docstrings and comments are unnecessarily used
  - [ ] Time complexity for non-algorithm tasks
  - [ ] Non IT question
  - [ ] Already answered question is asked in the second turn
- **Language Quality**
   - [ ] Grammar mistakes
  - [ ] The assistant jumps immediately to the code
  - [ ] The explanation in any markdown goes too wide (comparisons with other algorithms, usage...)
  - [ ] Acknowledge the users request 
  - [ ] Your latex uses \$..\$ (For latex you should use \\\\(...\\\\) )
  - [ ]  Empty markdown - does not provide any useful information (e.g., "Below is the code:", "Above is the implementation.")
- **Minor Issues: Let's Standardize**
  - [ ] The construct (Logic) of the sentence is not optimal
  - [ ] Backticks not used for namespaces and coding blocks, or used improperly
  - [ ] Text or coding cells are unnecessarily split
  - [ ] Missing headers, improper headers, no space below the header
  - [ ] More than one test example in Example usage
