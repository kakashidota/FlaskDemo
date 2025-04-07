# ✅ Solutions: Beginner-Friendly Flask Exercises

Here are the solutions to the Flask exercises. Compare your answers or use these to guide your learning!

---

## 🚀 Exercise 1: Dynamic Greeting

**app.py**
```python
from flask import Flask

app = Flask(__name__)

@app.route('/greet/<name>')
def greet(name):
    return f"<h1>Hello, {name}!</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

---

## 📝 Exercise 2: HTML Form Input

**app.py**
```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def form():
    return render_template('form.html')

@app.route('/submit', methods=['POST'])
def submit():
    name = request.form['name']
    return render_template('result.html', name=name)

if __name__ == '__main__':
    app.run(debug=True)
```

**templates/form.html**
```html
<form action="/submit" method="post">
  <input type="text" name="name" placeholder="Enter your name">
  <input type="submit" value="Submit">
</form>
```

**templates/result.html**
```html
<h1>Hello, {{ name }}!</h1>
```

---

## 🌐 Exercise 3: Multiple Routes

**app.py**
```python
from flask import Flask
app = Flask(__name__)

@app.route('/about')
def about():
    return "<h1>About Page</h1>"

@app.route('/contact')
def contact():
    return "<h1>Contact Page</h1>"

@app.route('/help')
def help():
    return "<h1>Help Page</h1>"

@app.route('/faq')
def faq():
    return "<h1>FAQ Page</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

---

## 📅 Exercise 4: Display Current Date

**app.py**
```python
from flask import Flask
import datetime

app = Flask(__name__)

@app.route('/date')
def date():
    today = datetime.date.today()
    return f"<h1>Today's date is {today}</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

---

## 🎯 Exercise 5: Simple Calculator

**app.py**
```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def calculator():
    return render_template('calculator.html')

@app.route('/result', methods=['POST'])
def result():
    num1 = float(request.form['num1'])
    num2 = float(request.form['num2'])
    operation = request.form['operation']
    if operation == 'add':
        result = num1 + num2
    elif operation == 'subtract':
        result = num1 - num2
    elif operation == 'multiply':
        result = num1 * num2
    elif operation == 'divide':
        result = num1 / num2
    return f"<h1>Result: {result}</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

**templates/calculator.html**
```html
<form action="/result" method="post">
  <input type="text" name="num1" placeholder="First number">
  <input type="text" name="num2" placeholder="Second number">
  <select name="operation">
    <option value="add">Add</option>
    <option value="subtract">Subtract</option>
    <option value="multiply">Multiply</option>
    <option value="divide">Divide</option>
  </select>
  <input type="submit" value="Calculate">
</form>
```

---

## 💬 Exercise 6: Personalized Message with GET Request

**app.py**
```python
from flask import Flask, request

app = Flask(__name__)

@app.route('/message')
def message():
    name = request.args.get('name')
    mood = request.args.get('mood')
    return f"<h1>Hello {name}, glad you're feeling {mood}!</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

---

## 🔁 Bonus Exercise: Page Counter

**app.py**
```python
from flask import Flask

app = Flask(__name__)
counter = 0

@app.route('/')
def home():
    global counter
    counter += 1
    return f"<h1>This page has been visited {counter} times.</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```