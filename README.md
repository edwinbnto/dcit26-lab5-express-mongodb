# DCIT 26 Laboratory 5: Express and MongoDB

## Project Description

This project is a Student Records REST API developed using Node.js, Express.js, MongoDB, and Mongoose. It allows users to create, retrieve, update, and delete student records stored in a MongoDB database.

## Technologies Used

- Node.js
- Express.js
- MongoDB
- Mongoose
- dotenv
- curl
- MongoDB Compass

## Project Structure

```text
dcit26-lab5-express-mongodb/
├── backend/
│   ├── models/
│   │   └── Student.js
│   └── server.js
├── .env
├── .env.example
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

## Installation and Setup

### 1. Install Dependencies

Make sure Node.js and MongoDB are installed on your computer.

Clone the repository and open the project folder:

```bash
git clone https://github.com/YOUR-USERNAME/dcit26-lab5-express-mongodb.git
cd dcit26-lab5-express-mongodb
```

Install the required packages:

```bash
npm install
```

If the development dependencies are not installed, run:

```bash
npm install --save-dev nodemon
```

### 2. Configure MongoDB

Make sure the MongoDB server is running.

Create a local `.env` file in the project root directory and add the following configuration:

```env
MONGODB_URI=mongodb://127.0.0.1:27017/lab5_students
PORT=5000
```

The `MONGODB_URI` specifies the MongoDB database connection, while `PORT` specifies the port used by the API server.

### 3. Configure Environment Variables

The `.env.example` file provides a template for the required environment variables.

Copy `.env.example` to `.env` and update the values if necessary.

### 4. Run the Server

Start the development server:

```bash
npm run dev
```

To run the server without nodemon:

```bash
npm start
```

The API will be available at:

`http://localhost:5000`

## Student Data Model

Each student record contains the following fields:

| Field | Data Type | Description |
|---|---|---|
| `fullName` | String | Required student name |
| `course` | String | Required course |
| `yearLevel` | Number | Required year level from 1 to 4 |
| `section` | String | Optional section |
| `createdAt` | Date | Automatically records the creation time |

## API Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/health` | Checks API health |
| GET | `/api/students` | Retrieves all students |
| GET | `/api/students/:id` | Retrieves a student by ID |
| POST | `/api/students` | Creates a new student |
| PUT | `/api/students/:id` | Updates a student by ID |
| DELETE | `/api/students/:id` | Deletes a student by ID |

## Sample Student Request

Use the following JSON body when creating a student using curl:

```json
{
  "fullName": "Alex Santos",
  "course": "BSIT",
  "yearLevel": 2,
  "section": "IT-2A"
}
```

Example POST request:

```bash
curl -i -X POST http://localhost:5000/api/students -H "Content-Type: application/json" -d "{\"fullName\":\"Alex Santos\",\"course\":\"BSIT\",\"yearLevel\":2,\"section\":\"IT-2A\"}"
```

## Testing

Test the API routes using curl in Windows Command Prompt.

Check the health endpoint:

```bash
curl -i http://localhost:5000/api/health
```

Retrieve all student records:

```bash
curl -i http://localhost:5000/api/students
```

The POST, GET-by-ID, PUT, and DELETE routes can also be tested using curl.

Verify that student records are saved in MongoDB using MongoDB Compass. Confirm that records remain available after restarting the API server.

## Error Handling

The API should return appropriate HTTP status codes:

- `200 OK` — Successful request.
- `201 Created` — Student record successfully created.
- `400 Bad Request` — Invalid input or malformed ID.
- `404 Not Found` — Student record does not exist.
- `500 Internal Server Error` — Unexpected server error.

## GitHub Submission

Repository name: `dcit26-lab5-express-mongodb`

The repository should contain the source code, `README.md`, `.gitignore`, and `.env.example`.

Do not commit the local `.env` file because it may contain private configuration values.

Submit the GitHub repository URL along with screenshots showing successful GET, POST, PUT, and DELETE requests and the saved student records in MongoDB Compass.

## Author

Name: YOUR FULL NAME

Course, Year, and Section: YOUR COURSE, YEAR, AND SECTION

Subject: DCIT 26 – Application Development and Emerging Technologies

Activity: Laboratory 5 – Express and MongoDB
