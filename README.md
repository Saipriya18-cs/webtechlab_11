# NodeMongoLab

**Student Name:** Saipriya Saravanan  
**Experiment:** Student CRUD operations using Node.js, Express and MongoDB  
**Database:** `studentdb`  
**Collection:** `students`

## Setup

1. Install Node.js and MongoDB.
2. Open this folder in Visual Studio Code.
3. In the terminal, run:

```bash
npm install
```

4. Make sure the MongoDB service is running.
5. Start the application:

```bash
npm start
```

For development with automatic restart:

```bash
npm run dev
```

Open `http://localhost:3000`.

## API endpoints

| Operation | Method | URL |
|---|---|---|
| Create student | POST | `/students` |
| View all students | GET | `/students` |
| View one student | GET | `/students/:regNo` |
| Update student | PUT | `/students/:regNo` |
| Delete student | DELETE | `/students/:regNo` |

## Example request body

Use `POST http://localhost:3000/students` with Body → raw → JSON:

```json
{
  "regNo": "URK23CS1001",
  "name": "Saipriya Saravanan",
  "department": "Computer Science and Engineering",
  "email": "your-email@example.com",
  "cgpa": 8.5
}
```

Replace the example register number and email with your own details before submitting.

## PowerShell test commands

```powershell
$student = @{
  regNo = "URK23CS1001"
  name = "Saipriya Saravanan"
  department = "Computer Science and Engineering"
  email = "your-email@example.com"
  cgpa = 8.5
} | ConvertTo-Json

Invoke-RestMethod -Uri "http://localhost:3000/students" -Method Post -ContentType "application/json" -Body $student
Invoke-RestMethod -Uri "http://localhost:3000/students" -Method Get
Invoke-RestMethod -Uri "http://localhost:3000/students/URK23CS1001" -Method Get

$update = @{
  name = "Saipriya Saravanan"
  department = "CSE"
  email = "your-email@example.com"
  cgpa = 9.0
} | ConvertTo-Json

Invoke-RestMethod -Uri "http://localhost:3000/students/URK23CS1001" -Method Put -ContentType "application/json" -Body $update
Invoke-RestMethod -Uri "http://localhost:3000/students/URK23CS1001" -Method Delete
```

**Note:** The commands above are examples to run locally. The application has not been run against your MongoDB installation from this package.
