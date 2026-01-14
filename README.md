# Issue Tracker Web App

A simple issue tracking web application built using HTML, CSS, JavaScript, Firebase Authentication, and Firebase Firestore, deployed on Vercel.

This project demonstrates real-world problem solving with authentication, data modeling, validation rules, and clean UI logic.

---

Live Demo
(After deployment, paste your Vercel URL here)

---

Features

- User Signup & Login using Firebase Auth (Email/Password)
- Display logged-in user's email
- Create issues with:
  - Title
  - Description
  - Priority (Low / Medium / High)
  - Status (Open / In Progress / Done)
  - Assigned To
  - Created By (auto from logged-in user)
  - Created Time (auto timestamp)
- Similar issue detection with confirmation prompt
- View all issues on dashboard
- Filter issues by Status and Priority
- Sorted by newest issues first
- Business rule enforced:
  - Issue cannot move directly from Open → Done
- Firebase Firestore as backend database
- Deployed on Vercel

---

Tech Stack

- Frontend: HTML, CSS, Vanilla JavaScript  
- Backend / Database: Firebase Firestore  
- Authentication: Firebase Auth (Email & Password)  
- Hosting: Vercel  
- Code Hosting: GitHub  

---

1.Why I chose HTML, CSS, and JavaScript

I chose vanilla HTML, CSS, and JavaScript to keep the project simple and avoid overengineering.  
This approach provides full control over logic, makes the code easier to understand, and demonstrates my strong hands-on without relying on frameworks.

---

2.Explain your Firestore data structure

I used a single collection named `issues`.

Each document contains:

```json
{
  "title": "Login button not working",
  "description": "Button does nothing when clicked",
  "priority": "High",
  "status": "Open",
  "assignedTo": "dev@email.com",
  "createdBy": "user@email.com",
  "createdTime": "2026-01-13T10:25:30.000Z"
}

----

3.Explain how you handled similar issues
When a user creates a new issue, the application checks existing issues stored in Firestore.
It compares the new issue’s title and description with previously created issues using simple text matching.
If a similar issue is found, the system shows a warning message and asks the user for confirmation before allowing the issue to be created.
This approach prevents accidental duplicates while keeping the solution simple and practical without overengineering.

----

4. Mention what was confusing or challenging?
The most challenging part of the project was integrating Firebase with vanilla JavaScript using ES modules.
Debugging issues related to imports, file structure, and Firebase configuration required careful attention.
Designing the Firestore data structure and implementing validation rules such as preventing Open → Done transitions also required thoughtful logic to ensure correctness.

-----

5. Mention what you would improve next
If I had more time, I would improve the project by adding full-text search for better similar-issue detection, pagination for large issue lists, and role-based access (such as Admin and User permissions).
I would also enhance the UI/UX using a design system and add features like edit/delete issue functionality and activity history for better usability.