# flask-heroku-guide
#How to Deploy a Simple Flask Web App to Heroku (Step-by-Step Guide)
 Author: Your Name
 Date: June 2025
 #Introduction
 This guide walks you through building and deploying a simple web application using Flask and
 Heroku. If youre new to backend development or want a project to showcase your technical writing
 skills, this is the perfect starting point.
 By the end, you'll have:- A basic Hello, World! app built with Flask- Your app deployed live using Heroku- A polished guide suitable for your portfolio
 #Prerequisites
 Before you begin, make sure you have:- Python 3.x- Git + GitHub account- Heroku account- Heroku CLI installed
 Tip: Use `python --version` and `git --version` to check your installations.
 #Project Overview
 Were building a Flask app that renders a simple HTML message. Here's the project structure:
 -flask-hello-app/
 -app.py
 -requirements.txt
 -Procfile
 -runtime.txt
 -templates/
     index.html
 Step 1: Set Up Your Project Locally
 1.1 Create Project Folder:
 mkdir flask-hello-app
 cd flask-hello-app
 1.2 Create the Flask App (app.py):
 from flask import Flask, render_template
 app = Flask(__name__)
 @app.route("/")
 def home():
    return render_template("index.html")
 if __name__ == "__main__":
    app.run(debug=True)
 1.3 Create templates/index.html:
 <!doctype html>
 <html>
  <head><title>Hello from Flask</title></head>
  <body><h1>Hello, World! Your Flask app is running.</h1></body>
 </html>
1.4 Add requirements.txt:
 Flask==2.3.3
 gunicorn==21.2.0
 Add runtime.txt:
 python-3.10.12
 Add Procfile:
 web: gunicorn app:app
 Step 2: Run the App Locally
 2.1 Create Virtual Environment:
 python -m venv venv
 source venv/bin/activate
 2.2 Install Dependencies:
 pip install -r requirements.txt
 2.3 Run the App:
 python app.py
 Visit http://127.0.0.1:5000 in your browser.
 Step 3: Deploy to Heroku
 3.1 Initialize Git and Push to GitHub:
 git init
 git add .
git commit -m "Initial commit"
 git remote add origin https://github.com/YOUR_USERNAME/flask-hello-app.git
 git branch -M main
 git push -u origin main
 3.2 Create a Heroku App:
 heroku login
 heroku create flask-hello-demo-app
 3.3 Push to Heroku:
 git push heroku main
 Verifying Success- You should see your app live in the browser- Check logs if errors occur:
 heroku logs --tail
 Quick Start Summary- Create app: python app.py- Install deps: pip install -r requirements.txt- Git init: git init && git add . && git commit -m "..."- Heroku deploy: heroku create && git push heroku main
 Next Steps- Add more pages to your Flask app- Connect to a database- Add templates and routing- Deploy with custom domain
Resources- Flask Documentation: flask.palletsprojects.com- Heroku CLI: devcenter.heroku.com/articles/heroku-cli- GitHub Markdown Guide: guides.github.com/features/mastering-markdown/
