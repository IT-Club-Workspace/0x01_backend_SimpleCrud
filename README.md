# 0x01_backend_SimpleCrud

## *Resources*

### *1. Database Setup*
- *File*: database.sql
- *Description*: SQL script to create the database and the users table.
```sql
  CREATE DATABASE contact_manager;
  USE contact_manager;

  CREATE TABLE users (
      id INT AUTO_INCREMENT PRIMARY KEY,
      name VARCHAR(100) NOT NULL,
      email VARCHAR(100) NOT NULL UNIQUE,
      phone VARCHAR(15),
      created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
  );
```
  

---

### *2. Database Connection*
- *File*: db_connection.php
- *Description*: PHP script to connect to the MySQL database.
  
  ```php
  <?php
  $host = 'localhost';
  $dbname = 'contact_manager';
  $username = 'root';
  $password = '';

  try {
      $conn = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
      $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  } catch (PDOException $e) {
      echo "Connection failed: " . $e->getMessage();
  }
  ?>
  ```

---

### *3. CSS for Styling*
- *File*: styles.css
- *Description*: Basic CSS to style the contact manager application.
- *Code*:
```css
  body {
      font-family: Arial, sans-serif;
      margin: 20px;
  }
  table {
      width: 100%;
      border-collapse: collapse;
  }
  table, th, td {
      border: 1px solid #ddd;
  }
  th, td {
      padding: 8px;
      text-align: left;
  }
  th {
      background-color: #f2f2f2;
  }
  form {
      margin-bottom: 20px;
  }
  input[type="text"], input[type="email"], input[type="submit"] {
      padding: 8px;
      margin: 5px 0;
      display: block;
  }
  a {
      text-decoration: none;
      color: #007bff;
  }
  a:hover {
      text-decoration: underline;
  }
  ```

---

### *4. Directory Structure*
Organize your files as follows:

contact_manager/
<br /> 
├<br />
├── database.sql<br />
├── db_connection.php<br />
├── styles.css<br />
├── create_user.php<br />
├── view_users.php<br />
├── edit_user.php<br />
├── delete_user.php<br />


---

## *Tasks*

### *Task 1: Create (Add a New User)*
- *File*: create_user.php
- *Description*: Build a form to add a new user to the users table.
- *Skills Tested*:
  - Form handling.
  - Input validation.
  - SQL INSERT query.
- *Points*: 20

---

### *Task 2: Read (View All Users)*
- *File*: ```view_users.php ```
- *Description*: Display all users from the users table in an HTML table.
- *Skills Tested*:
  - SQL SELECT query.
  - Displaying data in HTML.
- *Points*: 15

---

### *Task 3: Update (Edit a User)*
- *File*: ```edit_user.php```
- *Description*: Build a form to edit an existing user's details.
- *Skills Tested*:
  - Form handling with pre-filled data.
  - SQL UPDATE query.
- *Points*: 20

---

### *Task 4: Delete (Remove a User)*
- *File*: ```delete_user.php```
- *Description*: Implement functionality to delete a user from the users table.
- *Skills Tested*:
  - SQL DELETE query.
  - Handling confirmation before deletion.
- *Points*: 15

---

### *Task 5: Input Validation*
- *File*: create_user.php and edit_user.php
- *Description*: Add validation to ensure:
  - Name is not empty.
  - Email is valid and unique.
  - Phone number is optional but must be numeric if provided.
- *Skills Tested*:
  - Input validation using PHP.
- *Points*: 10

---

### *Task 6: Error Handling*
- *File*: All PHP files
- *Description*: Add error handling for database operations (e.g., display error messages if something goes wrong).
- *Skills Tested*:
  - Using try-catch blocks.
  - Displaying user-friendly error messages.
- *Points*: 10

---

### *Task 7: Styling*
- *File*: styles.css
- *Description*: Style the application to make it visually appealing.
- *Skills Tested*:
  - Basic CSS skills.
- *Points*: 10

---

## *Assumptions*
1. The user has a local server environment (e.g., XAMPP, WAMP, or MAMP) installed.
2. The user has basic knowledge of HTML, CSS, PHP, and SQL.
3. The database credentials (localhost, root, no password) are used for simplicity.
4. The application is for educational purposes and does not include advanced security measures like hashing passwords.

---

## *Scoring System*
- *Total Points*: 100
- *Grading*:
  - *90-100*: Excellent (A)
  - *80-89*: Good (B)
  - *70-79*: Satisfactory (C)
  - *60-69*: Needs Improvement (D)
  - *Below 60*: Fail (F)

---

## *Quiz Breakdown*
| *Task*               | *Points* | *Skills Tested*                              |
|-------------------------|------------|-----------------------------------------------|
| Create (Add User)       | 20         | Form handling, input validation, SQL INSERT |
| Read (View Users)       | 15         | SQL SELECT, HTML table rendering            |
| Update (Edit User)      | 20         | Form handling, SQL UPDATE                   |
| Delete (Remove User)    | 15         | SQL DELETE, confirmation handling           |
| Input Validation        | 10         | PHP validation logic                          |
| Error Handling          | 10         | try-catch, error messages                   |
| Styling                 | 10         | CSS skills                                    |
| *Total*               | *100*    |                                               |

---

This structure provides a clear roadmap for beginners to complete the CRUD application while testing their skills. Let me know if you need further adjustments! 🚀
