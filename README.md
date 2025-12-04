# NextPatient — Smart Queue & Token Management for Healthcare

NextPatient is a lightweight, fast, and modern hospital OPD queue and token management system built using Flask (Python) as the backend and HTML, CSS, JavaScript as the frontend.
It streamlines patient flow, reduces overcrowding, and ensures a seamless experience across OPD, Lab, and Pharmacy departments.

The project enables patients to register, get tokens, track their queue status in real-time, and view estimated waiting times. Staff can manage queues efficiently, call next patients, mark visits as completed, and monitor activity logs.

🚀 Features
👨‍⚕️ Patient Module

Full patient registration (Name, Phone, Age, Gender, Address)

Department selection: OPD, Lab, Pharmacy

Priority handling for elderly or emergency patients

Auto-generated token number

Live queue position tracking (polling every 4 seconds)

Estimated waiting time calculation

🧑‍💼 Staff Module

Dedicated staff dashboard for each department

View active queue in real-time

Call Next, Mark In-Progress, Complete, or Mark No-Show

Auto-updated queue ordering based on priority and arrival time

Token logs for auditing actions

📺 Display Screen (Waiting Area)

Full-screen “Now Serving” display

Shows next 5 upcoming tokens

Auto-refreshes every few seconds

🗄️ Backend (Flask)

REST API built using Flask + SQLAlchemy

Clean and modular architecture

MySQL database based on the official Hackathon PDF schema:

patients

tokens

counters

events

Secure and scalable design

🛠️ Tech Stack

Frontend:

HTML5

CSS3

JavaScript (Polling-based updates)

Backend:

Python Flask

SQLAlchemy ORM

Flask-CORS

MySQL Database (PyMySQL driver)

📂 Project Structure
NextPatient/
├─ backend/
│  ├─ app.py
│  ├─ models.py
│  ├─ config.py
│  ├─ .env
│  └─ requirements.txt
│
└─ frontend/
   ├─ templates/
   │  ├─ patient.html
   │  ├─ staff.html
   │  └─ display.html
   └─ static/
      ├─ css/
      └─ js/

🧪 API Endpoints (Overview)
Patient APIs

POST /api/patients — Register patient

POST /api/token — Generate token

GET /api/queue?department=OPD — Get current queue

Staff APIs

POST /api/token/<id>/action — Call / Start / Complete / No-Show

GET /api/events — View logs

Display

GET /api/now_serving?department=OPD

⚙️ Installation & Setup
1. Clone the repository
git clone https://github.com/yourusername/NextPatient.git
cd NextPatient/backend

2. Create virtual environment & install dependencies
python -m venv venv
source venv/bin/activate    # Windows: venv\Scripts\activate
pip install -r requirements.txt

3. Create .env file
SECRET_KEY=your-secret
DB_USER=root
DB_PASS=yourpassword
DB_HOST=127.0.0.1
DB_NAME=nextpatient

4. Import SQL schema into MySQL

Use the SQL file provided or run the SQL commands in the README.

5. Run the backend
python app.py

6. Access the system

Patient UI → http://127.0.0.1:5000/

Staff UI → http://127.0.0.1:5000/staff

Display Screen → http://127.0.0.1:5000/display

🎯 Why NextPatient?

Reduces patient waiting confusion

Improves hospital workflow efficiency

Lightweight + fast — perfect for clinics, hospitals, and labs

Built for hackathons with clean modular code

Easy to extend (authentication, analytics, dashboard, etc.)

📌 Future Enhancements

Role-based staff authentication

WebSocket real-time updates (instead of polling)

Multi-counter assignment algorithm

Analytics dashboard for hospital admins

SMS notifications (token called / next in line)

📝 License

This project is open-source under the MIT License.
