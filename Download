# Talkie_D_0.1
from flask import Flask, render_template, request, redirect, url_for
from flask_sslify import SSLify

app = Flask(Chatti)
sslify = SSLify(app)  # Enable SSL/TLS encryption

messages = []

@app.route('/')
def index():
    return render_template('index.html', messages=messages)

@app.route('/send', methods=['POST'])
def send():
    message = request.form['Username']
    messages.append(message)
    return redirect(url_for('index'))

if __name__ == '__main__':
    app.run(ssl_context='adhoc')  # Run the app using a self-signed certificate for testing

<!DOCTYPE html>
<html>
<head>
    <title>Messaging Platform</title>
</head>
<body>
    <h1>Messaging Platform</h1>
    <hr>
    {% block content %}
    {% endblock %}
</body>
</html>
{% extends 'base.html' %}

{% block content %}
    <form method="POST" action="/send">
        <input type="text" name="message" placeholder="Enter your message">
        <button type="submit">Send</button>
    </form>
    <hr>
    <ul>
        {% for message in messages %}
            <li>{{ message }}</li>
        {% endfor %}
    </ul>
{% endblock %}
pip install flask
python messaging_platform.py

<!DOCTYPE html>
<html>
<head>
    <title>Messaging Platform</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        h1 {
            text-align: center;
            margin-bottom: 20px;
        }
        form {
            margin-bottom: 20px;
        }
        input[type="text"] {
            width: 300px;
            padding: 5px;
            font-size: 14px;
        }
        button[type="submit"] {
            padding: 5px 10px;
            font-size: 14px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin-bottom: 10px;
            background-color: #f5f5f5;
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>Messaging Platform</h1>
    <hr>
    {% block content %}
    {% endblock %}
</body>
</html>
{% extends 'base.html' %}

{% block content %}
    <form method="POST" action="/send">
        <input type="text" name="message" placeholder="Enter your message">
        <button type="submit">Send</button>
    </form>
    <hr>
    <ul>
        {% for message in messages %}
            <li>{{ message }}</li>
        {% endfor %}
    </ul>
{% endblock %}
