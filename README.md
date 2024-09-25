# Firebase_auth


Here's a simple README.md file for a Firebase Authentication project using JavaScript:

Firebase Authentication - Simple Login and Sign Up
This project demonstrates basic authentication (login and sign-up) functionality using Firebase Authentication with JavaScript. It includes a simple interface where users can create an account and log in using email and password.

Features
Sign Up: New users can create an account using their email and password.
Login: Existing users can log in with their email and password.
Firebase Authentication: Powered by Firebase's Authentication services.
Prerequisites
Node.js installed on your system.
Firebase account – Sign up at firebase.google.com.
Firebase project setup – Create a new project in Firebase Console and enable Email/Password sign-in under Authentication.
Setup Instructions
1. Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/firebase-auth-example.git
cd firebase-auth-example
2. Install Firebase SDK
You can use Firebase CDN or install it via npm. For simplicity, we'll use the CDN version.

Add the following script in your HTML file:

html
Copy code
<script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-auth.js"></script>
3. Firebase Configuration
Create a Firebase project in the Firebase Console, and copy the Firebase configuration keys.

Add your Firebase config to the JavaScript file:

javascript
Copy code
// Firebase configuration
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_AUTH_DOMAIN",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_STORAGE_BUCKET",
    messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
    appId: "YOUR_APP_ID"
};

// Initialize Firebase
firebase.initializeApp(firebaseConfig);
4. Authentication Code
Sign Up (JavaScript)
javascript
Copy code
function signUp() {
    const email = document.getElementById('email').value;
    const password = document.getElementById('password').value;

    firebase.auth().createUserWithEmailAndPassword(email, password)
        .then((userCredential) => {
            // Signed up successfully
            console.log('User signed up:', userCredential.user);
        })
        .catch((error) => {
            console.error('Error during sign up:', error.message);
        });
}
Login (JavaScript)
javascript
Copy code
function login() {
    const email = document.getElementById('email').value;
    const password = document.getElementById('password').value;

    firebase.auth().signInWithEmailAndPassword(email, password)
        .then((userCredential) => {
            // Logged in successfully
            console.log('User logged in:', userCredential.user);
        })
        .catch((error) => {
            console.error('Error during login:', error.message);
        });
}
5. HTML Structure
html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Firebase Auth Example</title>
</head>
<body>
    <h1>Login / Sign Up</h1>
    
    <input type="email" id="email" placeholder="Enter your email" required>
    <input type="password" id="password" placeholder="Enter your password" required>
    
    <button onclick="signUp()">Sign Up</button>
    <button onclick="login()">Login</button>

    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-auth.js"></script>
    <script src="app.js"></script>
</body>
</html>
6. Run the Project
Open the index.html file in your browser.
