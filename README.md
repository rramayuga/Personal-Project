# Personal-Project

Project Console: https://console.firebase.google.com/project/neu-labtrack/overview
Hosting URL: https://neu-labtrack.web.app

Improved prompts
1. Improved Prompt (The "Gemini" Version)
Copy and paste this into Google Gemini to further refine your app's logic or generate code snippets.
System Role: You are an expert Full-Stack Developer specializing in Flutter/Firebase and React/Firebase.
Project Name: NEU Laboratory Usage Log
Objective: Build a web/mobile application to track faculty laboratory usage via QR Code, RFID simulation, and Google SSO.
User Personas:
Professor: Accesses the room by scanning a QR/RFID or logging in via Google Institutional Email. Receives a confirmation message.
Admin: Oversees the entire system via a dashboard with analytics, logs, and user management.
Core Features & Technical Requirements:
Authentication: Integration with Firebase Auth for Google Institutional Login.
Input Methods:
QR Code Scanner (Camera access).
RFID Simulation (A manual input field or button trigger for prototype testing).


Professor Workflow: After successful identification, check the user into a specific Room_ID. Display: "Thank you for using Room [Room Number]."
Admin Dashboard Requirements:
Summary Statistics: Visual cards showing: Total Sessions Today, Most Used Room, Currently Active Rooms, and Blocked Users.
Usage Logs: A searchable data table with filters for: Professor Name, Date Range (Daily/Weekly/Monthly/Custom), and Room Number.
User Management: Ability to toggle a "Blocked" status for specific professor accounts in Firestore.


UI/UX Preferences:
Clean, professional UI using Material Design 3.
Theme: NEU Institutional colors (if applicable) or a clean Blue/White professional palette.
Responsive layout for both Desktop (Admin) and Mobile (Professor).

2. UI Drafting (Instructions for Google AI Studio)
When you go to Google AI Studio, use the following specific instructions to generate your UI components.
For the Professor Login Screen:
"Generate a UI layout for a mobile-first login screen. Include a large 'Scan QR Code' button input field, and a 'Sign in with Google' button. Use a clean, modern aesthetic with plenty of white space."
For the Admin Dashboard:
"Generate a dashboard layout for a web app. The top should have four 'Stats Cards' (Total Logs, Active Professors, Most Used Lab, Blocked Users). Below that, a high-density data table for usage logs with a search bar and a date-range picker filter."

3. Firebase Studio Implementation (Data Structure)
When you feed the prompt into Firebase Studio or manually configure your database, use this Firestore Schema:
Collection: 
uid: String (Primary Key)
name: String
email: String (Google Email)
role: String ("Professor" or "Admin")
isBlocked: Boolean
qrCodeData: String (Unique ID linked to their ID card)
Collection: 
logId: String
professorId: Reference (Points to users)
professorName: String
roomNumber: String
timestampIn: Timestamp
timestampOut: Timestamp
duration: Number (minutes)
Collection: 
roomId: String
roomName: String
status: String ("Occupied", "Available")

4. Logic for "QR Simulation"
Since physical QR reading requires specific hardware drivers (Web API), for your March 2026 project, use this logic in your code:
codeJavaScript
// Example QRSimulation Logic
const simulateQR = (qrSerial) => {
   const user = findUserByQR(qrSerial);
   if (user.isBlocked) {
       alert("Access Denied: Account Blocked.");
   } else {
       logUsage(user.uid, "Lab 402");
       alert(`Thank you for using Room 402, Professor ${user.name}!`);
   }
}
Next Steps for You:
Open Google AI Studio: Use the UI prompts from Step 2 to get your CSS/HTML or Flutter code.
Open Firebase: Create a project named "NEU-Lab-Log."
Refine with Gemini: Ask Gemini, "Write a Firestore Security Rule that allows only Admins to change the 'isBlocked' status of a user."
Connect: Paste the generated code from AI Studio into your IDE and link the Firebase Config.

