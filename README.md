
# Employee Registration Web Application

A full-stack employee registration application built with **Next.js** frontend and **FastAPI** backend, persisting data into MongoDB. This project demonstrates clean, simple code using React hooks for state management and environment variables for configuration.

---

## Features

- Responsive React form for employee registration
- State management with React hooks (`useState`)
- FastAPI backend with Pydantic data validation
- MongoDB data persistence with credentials managed via `.env`
- Next.js API route proxy to avoid CORS issues
- Clear error handling and user feedback

---

## Repository Structure

employee-registration/
├── backend/
│ ├── app/
│ │ └── main.py # FastAPI application
│ ├── .env # Backend environment variables
│ ├── requirements.txt # Python dependencies
│ └── ...
├── frontend/
│ ├── components/FormComponent.jsx # React form component with hooks
│ ├── src/
│ │ └── app/api/route.js # Next.js API route proxy
│ ├── package.json
│ └── ...
├── README.md
└── ...

text

---

## Prerequisites

- [Node.js](https://nodejs.org/en/download/) 16+ (for Next.js)
- [Python](https://www.python.org/downloads/) 3.9+
- [MongoDB](https://www.mongodb.com/try/download/community) (local or MongoDB Atlas)
- `pip` for Python packages

---

## Getting Started — Run Locally

### 1. Clone the Repository

git clone <repository-url>
cd employee-registration

text

---

### 2. Setup MongoDB

- For **local MongoDB**, ensure the server is running.
- For **Atlas**, create a cluster, whitelist your IP, and get the connection string.

---

### 3. Backend Setup (FastAPI)

cd backend
python -m venv venv

Activate venv:
Windows
venv\Scripts\activate

Mac/Linux
source venv/bin/activate

pip install -r requirements.txt

text

- Create a `.env` file inside the `backend` folder:

MONGODB_URI=<your_mongodb_connection_uri>
MONGODB_DB=EmployeesReg
MONGODB_COLLECTION=workers

text

- Run the backend server:

uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

text

- Confirm backend is up at [http://localhost:8000/docs](http://localhost:8000/docs)

---

### 4. Frontend Setup (Next.js)

cd ../frontend
npm install
npm run dev

text

- Open your browser at [http://localhost:3000](http://localhost:3000)
- The form submits data to your Next.js API route (`/api`), which proxies to FastAPI.

---

## Development Notes

- The React form uses hooks (`useState`) for clean state management.
- Environment variables secure your database credentials (no secrets in code).
- Next.js API route (`src/app/api/route.js`) proxies requests to FastAPI — avoids CORS errors.
- Backend validates all incoming data with Pydantic ensuring data integrity.
- Always check browser console and network tabs if you encounter errors.

---

## Troubleshooting

- **Network/server errors on form submission:**
  - Verify FastAPI backend running and reachable at port 8000.
  - Confirm backend `.env` variables are correct.
  - Check proxy URL and ports in frontend fetch calls.
  - Restart backend/frontend after any config changes.
- **CORS issues:**
  - Use the Next.js API proxy route (already set up) to avoid CORS.
- **Data validation errors:**
  - Confirm frontend sends correctly typed JSON (numbers, booleans).

---

## Technologies Used

| Layer           | Tools/Frameworks                   |
|-----------------|----------------------------------|
| Frontend        | Next.js, React, React hooks      |
| Backend         | FastAPI, Pydantic                |
| Database        | MongoDB                         |
| Proxy           | Next.js API Routes               |
| Environment     | `.env` management via Pydantic settings  |

---

## License

This project is licensed under the MIT License.

---

## Contact & Support

For issues and contributions, please open an issue or pull request on this repository.  
Happy coding! 🚀
