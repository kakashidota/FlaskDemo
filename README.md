# 🧪 Simple Flask Website with Template Rendering

This guide will help you create a simple Flask website with multiple endpoints. The home (`/`) route renders an HTML template, and other routes return basic HTML headers.

---

## 🧱 Project Structure

```
simple_flask_app/
├── app.py
└── templates/
    └── index.html
```

---

## 📄 Step 1: `app.py`

Create a file named `app.py`:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/about')
def about():
    return "<h1>About</h1>"

@app.route('/contact')
def contact():
    return "<h1>Contact</h1>"

@app.route('/services')
def services():
    return "<h1>Services</h1>"

@app.route('/blog')
def blog():
    return "<h1>Blog</h1>"

if __name__ == '__main__':
    app.run(debug=True)
```

---

## 📄 Step 2: `templates/index.html`

Inside a folder named `templates`, create `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Home</title>
</head>
<body>
    <h1>Home</h1>
</body>
</html>
```

---

## ▶️ Step 3: Run the App

Install Flask if you haven't already:

```bash
pip install flask
```

Then run the app:

```bash
python app.py
```

Open your browser and navigate to:

- `http://127.0.0.1:5000/` → Home (renders HTML template)
- `http://127.0.0.1:5000/about` → About
- `http://127.0.0.1:5000/contact` → Contact
- `http://127.0.0.1:5000/services` → Services
- `http://127.0.0.1:5000/blog` → Blog
