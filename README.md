# Hospital-Management-System

OVERVIEW:

This Python script creates a command-line Hospital Management System linked to a MySQL database. It enables full CRUD operations—adding, viewing, updating, and deleting patient records—offering a practical demonstration of database integration and management logic.

FEATURES:

This code features a user-friendly, menu-driven interface that loops continuously, allowing for seamless interaction without restarting. It connects directly to a MySQL database to perform full CRUD operations, enabling users to add, view, search, and delete patient records permanently. A standout feature is the smart update logic, which allows users to press "Enter" to keep existing data during modifications, while basic validation ensures operations only occur on valid IDs. Additionally, the system formats data into a clean, tabular layout for easy reading.

TECHNOLOGIES/TOOLS USED:

This project utilizes Python for the core logic and interface, integrated with a MySQL database for persistent storage. The connection is established using the mysql.connector library, allowing the script to execute standard SQL queries for all data management tasks.

STEPS TO INSTALL AND RUN THE PROJECT:

To set up and run this project, first ensure that Python and MySQL are installed on your system, then execute pip install mysql-connector-python in your terminal to install the required driver. Next, open your MySQL SQL editor to create a database named Hospital_Management and a Patients table containing columns for ID, name, age, gender, and disease to match the code's structure. Before running the script, you must manually update the password parameter within the mysql.connector.connect function in the Python code to match your local MySQL root password. Finally, save the file with a .py extension and execute it via your command line using python filename.py to launch the application.

INSTRUCTION FOR TESTING:

Add a test patient using Option 1 and verify it appears in the list with Option 2. Then, use that same patient's ID to check if Option 4 updates the details and Option 5 successfully removes the record.
