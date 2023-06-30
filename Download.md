from flask import Flask, render_template, request, redirect, url_for, send_file
from flask_sslify import SSLify

app = Flask(__name__)
sslify = SSLify(app)  # Enable SSL/TLS encryption

messages = []

@app.route('/')
def index():
    return render_template('index.html', messages=messages)

@app.route('/send', methods=['POST'])
def send():
    message = request.form['message']
    messages.append(message)
    return redirect(url_for('index'))

@app.route('/download')
def download():
    # Generate a text file containing all the messages
    message_text = "\n".join(messages)
    file_path = "messages.txt"
    with open(file_path, "w") as file:
        file.write(message_text)

    return send_file(file_path, as_attachment=True)

if __name__ == '__main__':
    app.run(ssl_context='adhoc')  # Run the app using a self-signed certificate for testing
