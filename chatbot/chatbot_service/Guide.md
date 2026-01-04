Admin Login Guide
This guide explains how to login as an administrator in the MedVault application.

1. Register an Admin Account
If you haven't already registered an admin account, you need to do so via the backend API using Postman or any other API client.

Method: POST
URL: http://localhost:8080/api/auth/register/admin
Headers: Content-Type: application/json
Body:
{
  "email": "admin@medvault.com",
  "password": "securePassword123",
  "firstName": "Admin",
  "lastName": "User",
  "phone": "9876543210",
  "department": "IT Operations"
}
2. Access the Admin Portal
The admin portal has a dedicated entry point in the frontend.

URL: http://localhost:5173/admin.html
NOTE

Ensure both the backend (Spring Boot) and frontend (Vite) are running.

3. Login
Use the credentials you registered (or the ones provided in the 
README.md
):

Email: admin@medvault.com
Password: securePassword123
Once logged in, you will be redirected to the Admin Dashboard where you can manage patients, doctors, and appointments.

MedBuddy Chatbot Guide
MedBuddy is an AI-powered healthcare assistant that helps users with quick information.

1. Setup and Start the Chatbot
The chatbot is a FastAPI service that needs to be running separately.

Open a new terminal and navigate to the chatbot directory:
cd chatbot/chatbot_service
Install dependencies:
pip install -r requirements.txt
Start the service:
python main.py
The chatbot will start on http://localhost:8001.

2. How the Chatbot Works
The chatbot uses an intent-based system with fuzzy matching to provide accurate responses:

Knowledge Base: All doctor data, FAQs, and medicine interactions are stored in 
knowledge_base.json
.
Logic: The 
chat_service.py
 processes messages to identify what the user wants (e.g., searching for a doctor, checking symptoms).
Frontend Integration: The frontend (in 
index.html
) communicates with the chatbot via the /api/chat endpoint.
3. Key Capabilities
Doctor Search: Ask "Find a dentist" or "Is there a cardiologist?"
Medicine Safety: Ask "Can I take Aspirin and Ibuprofen together?"
Side Effects: Ask "What are the side effects of Metformin?"
Symptom Triage: Ask "I have fever and sore throat" (MedBuddy will suggest the right specialist).
General FAQs: Ask about appointment booking, record uploading, etc.