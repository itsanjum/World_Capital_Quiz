Quiz Application

This project is a simple quiz application built with Node.js, Express, and PostgreSQL. It retrieves country-capital data from a PostgreSQL database and displays them as questions in the app. Users can submit answers, and their total correct answers are displayed.

Prerequisites

To run this application, ensure you have the following installed:

Node.js - (v14.x or higher recommended)

PostgreSQL - (v12.x or higher recommended)

NPM - Comes bundled with Node.js.

Setup Instructions

Step 1: Clone the Repository

git clone <repository_url>
cd <repository_folder>

Step 2: Install Dependencies

Run the following command in the project root to install the required npm modules:

npm install

Step 3: Configure the Database

Create a PostgreSQL database named world.

Create a table named capitals with the following schema:

CREATE TABLE capitals (
  id SERIAL PRIMARY KEY,
  country VARCHAR(255) NOT NULL,
  capital VARCHAR(255) NOT NULL
);

Insert some sample data into the table:

INSERT INTO capitals (country, capital)
VALUES ('France', 'Paris'), ('United Kingdom', 'London'), ('United States of America', 'New York');

Update the db configuration in index.js with your PostgreSQL credentials:

const db = new pg.Client({
  user: "<your_username>",
  host: "localhost",
  database: "world",
  password: "<your_password>",
  port: 5432
});

Step 4: Start the Server

Run the following command to start the server:

npm start

The application will run at: http://localhost:3000

Application Features

Displays a random country from the database and prompts the user to enter its capital.

Validates the user’s answer and keeps track of the total correct answers.

Uses EJS for server-side rendering of the views.

Retrieves quiz questions dynamically from a PostgreSQL database.

Project Structure

|-- public/
|   |-- styles.css   # Static assets (CSS)
|-- views/
|   |-- index.ejs    # EJS template for the quiz page
|-- index.js         # Main server file
|-- package.json     # NPM configuration file
|-- README.md        # Project documentation

Dependencies

express: Web framework for Node.js.

body-parser: Middleware to parse incoming request bodies.

pg: PostgreSQL client for Node.js.

ejs: Templating engine for generating HTML.

Troubleshooting

Database Connection Errors:

Verify that PostgreSQL is running.

Ensure the database credentials in index.js are correct.

Server Crashes:

Check the console logs for error messages.

Verify all dependencies are installed by running npm install.

Future Enhancements

Add user authentication for personalized score tracking.

Implement additional question categories.

Enhance the UI with better styling.

Provide an API endpoint for fetching questions dynamically.

License

This project is licensed under the MIT License. Feel free to use and modify it as needed.

