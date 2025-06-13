
# 🚀 How to Deploy a Simple Flask Web App to Heroku

**Author:** Your Name  
**Date:** June 2025  
**Estimated Reading Time:** 10–15 minutes

---

## 🧭 Introduction

This guide walks you through building and deploying a simple web application using **Flask** and **Heroku**.

By the end, you'll have:
- A basic “Hello, World!” app built with Flask
- Your app deployed live using Heroku
- A polished guide suitable for your portfolio

---

## ⚙️ Prerequisites

Before you begin, make sure you have:

| Tool         | Version | Purpose            |
|--------------|---------|--------------------|
| Python       | 3.x     | Programming language |
| Git          | Latest  | Version control    |
| GitHub       | —       | Host source code   |
| Heroku CLI   | Latest  | Deploy app         |
| Heroku account | —     | Host web app       |

> Tip: Use `python --version` and `git --version` to verify installations.

---

## 📂 Project Overview

We’re building a Flask app that renders a simple HTML message. Here's the structure:

```
flask-hello-app/
├── app.py
├── requirements.txt
├── Procfile
├── runtime.txt
└── templates/
    └── index.html
```

---

## 🏗 Step 1: Set Up Your Project Locally

### 1.1 Create Project Folder
```bash
mkdir flask-hello-app
cd flask-hello-app
```

### 1.2 Create the Flask App (`app.py`)
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("index.html")

if __name__ == "__main__":
    app.run(debug=True)
```

### 1.3 Create an HTML Template (`templates/index.html`)
```html
<!doctype html>
<html>
  <head>
    <title>Hello from Flask</title>
  </head>
  <body>
    <h1>Hello, World! Your Flask app is running.</h1>
  </body>
</html>
```

### 1.4 Add Dependency and Config Files

`requirements.txt`
```
Flask==2.3.3
gunicorn==21.2.0
```

`runtime.txt`
```
python-3.10.12
```

`Procfile` (no file extension):
```
web: gunicorn app:app
```

---

## 🔧 Step 2: Run the App Locally

### 2.1 Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 2.2 Install Dependencies
```bash
pip install -r requirements.txt
```

### 2.3 Run the App
```bash
python app.py
```

Open your browser and go to: `http://127.0.0.1:5000`

---

## ☁️ Step 3: Deploy to Heroku

### 3.1 Initialize Git and Push to GitHub
```bash
git init
git add .
git commit -m "Initial commit"
```

Create a GitHub repo and link it:
```bash
git remote add origin https://github.com/YOUR_USERNAME/flask-hello-app.git
git branch -M main
git push -u origin main
```

### 3.2 Create a Heroku App
```bash
heroku login
heroku create flask-hello-demo-app
```

### 3.3 Deploy to Heroku
```bash
git push heroku main
```

Visit the Heroku URL (e.g., `https://flask-hello-demo-app.herokuapp.com`)

---

## ✅ Verifying Success

- Your app should be live online
- For troubleshooting:
```bash
heroku logs --tail
```

Common fixes:
- Ensure your `Procfile` has no extension
- Confirm correct Python version in `runtime.txt`

---

## 📌 Quick Start Summary

| Task             | Command                                     |
|------------------|---------------------------------------------|
| Create App       | `python app.py`                             |
| Install Deps     | `pip install -r requirements.txt`           |
| Git Init         | `git init && git add . && git commit -m`    |
| Deploy to Heroku | `heroku create && git push heroku main`     |

---

## 🧭 Next Steps

- Add additional Flask routes/pages
- Connect to a database (SQLite/PostgreSQL)
- Add error handling and testing
- Deploy with a custom domain

---

## 📚 Resources

- [Flask Documentation](https://flask.palletsprojects.com/)
- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)
- [Markdown Guide](https://www.markdownguide.org/)

---

## ✨ Author Notes

Thanks for reading!  
Feel free to fork this guide or connect with me on [LinkedIn](#).
