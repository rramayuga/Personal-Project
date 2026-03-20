# NEU LABTRACK

Project Console: https://console.firebase.google.com/project/neu-labtrack/overview
Hosting URL: https://neu-labtrack.web.app
🔬 NEU LabTrack - Features List
An advanced, real-time Laboratory Management System built for New Era University, designed to automate faculty usage logging, room occupancy tracking, and security monitoring.
👤 User Personas
Admins: Manage the entire laboratory ecosystem, monitor security, and generate analytics.
Professors: Seamlessly log usage via QR or RFID and manage personal session history.
🚀 Core Features
1. Smart Authentication & Routing
Google Institutional SSO: Secure login using university email addresses via Firebase Authentication.
Role-Based Access Control (RBAC): Automatic redirection based on user privilege:
Admin Emails 
→
→
 Command Center
Professor Emails 
→
→
 Faculty Dashboard
Real-Time Security Gate: Instant session termination if an Admin blocks a user account while they are active.
2. High-Tech Check-In System
Deep-Link QR Scanning: Admins generate unique QR codes for doors. When a professor scans via their native phone camera:
It opens the app.
Recognizes the Room ID.
Automatically records the log post-authentication (Zero-Tap Logging).
Integrated Web Scanner: Built-in camera scanner within the dashboard for professors already logged in.
RFID Simulation: Manual entry support for RFID Tag Hex codes to simulate physical card tapping.
Active Session Management: Prevents double check-ins. Professors must "Check-Out" of a room before entering another, ensuring data accuracy.
3. Admin Command Center
Dynamic Room Directory: A live grid showing all laboratories (M101-M120 and beyond).
Live Occupancy Tracking: Room cards turn Red and display the Full Name of the occupant in real-time.
Laboratory Registration: Admin can manually register new rooms to the permanent directory.
Faculty Management: A dedicated panel to monitor all users with the ability to Block/Restore access instantly.
4. Advanced Analytics & Reporting
Visual Usage Charts: Real-time bar graphs (via Chart.js) comparing:
Frequency: Which rooms are visited most often.
Duration: Which rooms have the highest total "Time-on-Lab" in minutes.
Data Export (Audit Ready):
CSV Export: For deep data analysis in Excel or Google Sheets.
PDF Export: Professional, branded reports for university records (via jsPDF).
5. Security & Monitoring
Unauthorized Access Alerts: A "Security Alert" log that captures and notifies the Admin of login attempts from blocked users.
Firestore Indexing: Optimized data queries for high-speed performance even with thousands of records.
Protected Admin Routes: Hard-coded security checks prevent non-admin users from manually accessing the /admin.html URL.
🛠️ Technical Stack
Frontend: HTML5, Tailwind CSS (Mobile-Responsive), JavaScript (ES6+).
Backend: Firebase (Firestore, Authentication, Hosting).
Libraries:
Chart.js: Data Visualization.
QRCode.js: Static QR Generation.
Html5-QRCode: Live Camera Scanning.
jsPDF & AutoTable: Document Generation.
📅 Project Timeline
Development Start: March 16, 2026
Current Version: 1.5 (Stable)
Deployment: Firebase Hosting (neu-labtrack.web.app)
