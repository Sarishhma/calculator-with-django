# 🧮 Django Calculator

A simple calculator web app built with **Python** and the **Django framework**.  
It allows users to perform basic arithmetic operations like addition, subtraction, multiplication, and division.

---

## 🚀 Features

- Perform basic arithmetic operations ( + − × ÷ )
- Handles invalid inputs and errors gracefully
- Built with clean HTML using Django’s templating system
- Simple and beginner-friendly project to understand Django forms and views

---

## 💻 Tech Stack

- **Backend:** Python, Django
- **Frontend:** HTML, CSS (you can mention Tailwind or Bootstrap if you used them)
- **Templating:** Django Templates

🧠 How It Works
This Django calculator handles user input through a form and processes basic arithmetic operations using backend logic.

Here’s a step-by-step breakdown of how it works:

1. User Input via Form
The user enters two numbers and selects an operation (Add, Subtract, Multiply, Divide) in the browser.

When they submit the form, a POST request is sent to the server.

2. Django View Handles Request
Inside the view (calculator_view), the following happens:


if request.method == 'POST':
The server detects a form submission.
num1 = request.POST.get('num1')
num2 = request.POST.get('num2')
operation = request.POST.get('operation')
It extracts the two numbers and the selected operation from the form.

3. Input Validation
if num1.replace('.', '', 1).isdigit() and num2.replace('.', '', 1).isdigit():
This line checks whether both values are valid numbers (integers or decimals).

If invalid input is detected (like letters or empty fields), an error is shown.

4. Performing the Operation
Depending on the selected operation, the correct arithmetic is done:
if operation == 'add':
    result = num1 + num2
elif operation == 'subtract':
    result = num1 - num2
elif operation == 'multiply':
    result = num1 * num2
elif operation == 'divide':
    result = num1 / num2 if num2 != 0 else "Can't divide by 0"
Division includes a special check to avoid dividing by zero.

5. Rendering the Result
return render(request, 'calculator/calculator.html', {'result': result, 'error': error})
The view sends either the result or an error back to the HTML template.

The page reloads and displays the result right below the form.

✅ Example
If a user enters:
Number 1: 8
Number 2: 2
Operation: Divide
The backend will process 8 / 2 and return:
Result: 4.0
made by sarishma .
