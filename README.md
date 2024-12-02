 README: University Timetable Web Application
 

 Project Overview
This project is a University Timetable Web Application that allows students to view their class schedules based on their academic level. The application uses Flask as the backend framework, PostgreSQL as the database, and HTML/CSS for the frontend. The system supports CRUD operations for the timetable data and dynamically fetches schedules from the database.


 Key Features
1. Home Page: A simple form where students input their academic level.
2. Timetable Display: Displays a detailed schedule, including course name, instructor, day, time, room, and level.
3. Dynamic Integration: Fetches data from the database based on the user's selected level.


 Technology Stack
- Frontend: HTML, CSS, Jinja2 Templates
- Backend: Flask (Python)
- Database: PostgreSQL
- Driver: `pg8000`


 How to Run the Project
1. Install Dependencies:
   - Ensure Python 3.x is installed on your system.
   - Install Flask:  
     ```
     pip install flask
     ```
   - Install the PostgreSQL driver:  
     ```
     pip install pg8000
     ```

2. Set Up the PostgreSQL Database:
   - Create a new database named `Rustam_schedual`:
     ```
     CREATE DATABASE Rustam_schedual;
     ```
   - Create the `Timetable` table:
     ```sql
     CREATE TABLE Timetable (
         course_id SERIAL PRIMARY KEY,
         course_name VARCHAR(255),
         instructor VARCHAR(255),
         day VARCHAR(50),
         time VARCHAR(50),
         room VARCHAR(50),
         level INT
     );
     ```
   - Insert sample data into the `Timetable` table:
     ```sql
     INSERT INTO Timetable (course_name, instructor, day, time, room, level) VALUES
     ('Operating Systems', 'Boeva, Sok', 'Monday', '04:30 PM', '304', 2),
     ('Social Engineering', 'Guseynov', 'Thursday', '11:30 AM', '406', 1),
     ('Computer Languages', 'Bekov, San', 'Wednesday', '02:00 PM', '114', 3),
     ('Media, Diversity, and Society', 'Isner, Vin', 'Wednesday', '07:00 PM', 'WebNet+', 3),
     ('Science in the News', 'Attanayake', 'Friday', '04:30 PM', 'WebNet+', 2);
     ```

3. Run the Flask Application:
   - Start the Flask server:
     ```
     python app.py
     ```
   - The app will run on `http://127.0.0.1:5000`.

4. Access the Application:
   - Open a web browser and navigate to `http://127.0.0.1:5000`.
   - Enter your level (e.g., 1, 2, or 3) to view the timetable for that level.


 Description of the Process
1. Backend Development:
   - Created Flask routes:
     - `index`: Handles the form for level input.
     - `timetable`: Fetches and displays timetable data from the database.
   - Connected to PostgreSQL using the `pg8000` library.
   - Wrote SQL queries to retrieve data for specific levels.

2. Frontend Development:
   - Designed an input form for the home page using HTML.
   - Used Jinja2 templating to dynamically render timetable data.

3. Integration:
   - Connected the form to the `/timetable` route.
   - Passed user input from the frontend to the backend and displayed the result dynamically.


 Problems Faced
1. Database Connection Error:
   - Faced a `database "Rustam_schedual" does not exist` error.
   - Solution: Ensured the database was created and double-checked the database name.

2. Method Not Allowed Issue:
   - Initially, the form submission used a `GET` method for the `/` route, which caused errors.
   - Solution: Updated the form method to `POST` and handled it properly in Flask.

3. Empty Query Parameter:
   - When users navigated directly to `/timetable` without selecting a level, it caused an error.
   - Solution: Added a check to ensure a level is provided and handled the error gracefully.

4. HTML Styling:
   - The pages initially looked very simple and plain.
   - Solution: Added CSS to improve the overall design.

5. Database Driver Setup:
   - Faced issues configuring `pg8000` as the PostgreSQL driver.
   - Solution: Installed the library and ensured the database credentials were correct.


 Future Improvements
- Add authentication to allow students to log in and see personalized timetables.
- Enable admin functionality to add, edit, or delete timetable data directly through the app.
- Implement a search function to filter courses by name or instructor.
- Use a CSS framework like Bootstrap for a more modern and responsive design.


 Credits
Project by Rustam Yakubov, Web Application Development Enthusiast. 

If you have any questions or encounter any issues, feel free to reach out!