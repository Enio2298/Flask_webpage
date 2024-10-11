# Flask webpage

This is a simple Flask application that allows users to submit a form with personal information such as first name, last name, email, date, and occupation. Upon form submission, the data is saved to a SQLite database, and a confirmation email is sent to the user.
Features

    Submit personal details through an HTML form.
    Save the form data to a SQLite database.
    Send a confirmation email to the user after form submission.
    Flash a success message to the user upon successful submission.

Requirements

To run this project, you need to have the following installed:

    Python 3.x
    Flask
    Flask-SQLAlchemy
    Flask-Mail

Setup Instructions
1. Clone the repository

bash

git clone https://github.com/your-repo/flask-form-submission.git
cd flask-form-submission

2. Install dependencies

Make sure you have pip installed, then run:

bash

pip install Flask Flask-SQLAlchemy Flask-Mail

3. Configure the application

The configuration parameters such as the secret key, database URI, and email server settings are set in the code. These can be modified as necessary:

    SECRET_KEY: Used for session management and to flash messages securely.
    SQLALCHEMY_DATABASE_URI: Defines the SQLite database location.
    MAIL_SERVER, MAIL_PORT, MAIL_USE_SSL, MAIL_USERNAME, MAIL_PASSWORD: These parameters are used for email functionality. Ensure the correct Gmail settings are in place.

Note: Remember to replace the Gmail username and password with valid credentials, or use environment variables for better security.
4. Run the application

Create the database tables and start the Flask development server:

bash

python app.py

The application will be available at http://127.0.0.1:5001.
5. Access the application

Navigate to the following URL in your browser to view the form:

arduino

http://127.0.0.1:5001

6. Submit the form

Fill in the form with your details and hit the submit button. The data will be saved in the SQLite database, and you will receive a confirmation email if the email service is configured correctly.
Application Structure

    app.py: Main application file that contains the Flask routes, form processing logic, and email sending functionality.
    datab.db: SQLite database file that stores the form submissions (created automatically when you run the app).
    templates/index.html: The HTML form for data submission.

Key Components:

    Flask Setup:
        Flask: The web framework used to run the application.
        Flask-SQLAlchemy: ORM used for interacting with the SQLite database.
        Flask-Mail: Handles the email functionality for sending confirmation messages.

    Routes:
        /: The main route where the form is displayed and processed. Handles both GET and POST requests.

    Database:
        SQLite is used to store the form submissions. The Form model defines the structure of the data.

    Email:
        Once a form is submitted, the app sends a confirmation email using Flask-Mail.

Security Note

Sensitive information such as the Gmail username and password is hardcoded in the app. For production use, it's strongly recommended to move these configurations to environment variables or a separate configuration file.
