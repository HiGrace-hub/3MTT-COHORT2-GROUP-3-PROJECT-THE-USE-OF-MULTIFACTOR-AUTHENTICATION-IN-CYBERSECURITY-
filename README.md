# 3MTT-COHOST2-GROUP-3-PROJECT-THE-USE-OF-MULTIFACTOR-AUTHENTICATION-IN-CYBERSECURITY-
Embedding Multi-factor authentication into simple login template in securing unauthorised access in cybersecurity

Here’s a breakdown of how the multi-factor authentication (MFA) login process was implemented across four HTML files:

1. Login Page (index.html)
Purpose: Collects the username and password.
Process:
The user enters their credentials in the input fields for "Username" and "Password."
After entering the details, clicking the "Login" button redirects to the biometric verification page (biometric.html) through an anchor link.
2. Biometric Verification Page (biometric.html)
Purpose: Uses the device’s camera for facial verification as a second authentication factor.

Process:

Displays a button labeled "verify biometric" to activate the camera.
When the button is clicked, the JavaScript function turnOnCamera() attempts to access the user's camera using the getUserMedia API.
If the camera is accessible, the video stream is displayed on the page.
The user can click the "Submit" button, which leads to the success confirmation page (success.html) upon successful verification.
JavaScript Code Explanation:

javascript
Copy code
async function turnOnCamera() {
  try {
    const stream = await navigator.mediaDevices.getUserMedia({ video: true });
    const videoElement = document.getElementById("camera");
    videoElement.srcObject = stream;
  } catch (error) {
    console.error("Error accessing the camera:", error);
    alert("Could not access the camera. Please check your browser permissions.");
  }
}
The function prompts the browser to request camera access.
If access is denied or an error occurs, it displays an alert message.
3. Successful Login Confirmation Page (success.html)
Purpose: Notifies the user of a successful login after passing both factors (password and facial verification).
Process:
Displays a confirmation message: "Login Successful!"
Provides a link to return to the initial login page.
4. Styling and Animation (style.css)
The layout and design are controlled by the linked style.css file, making the form look aesthetically pleasing with animations and responsive styles.
Overall Flow
User enters credentials on the login page.
If credentials are correct, they are redirected to the biometric verification page.
The camera is used for facial verification.
Upon successful face verification, the user is redirected to the success page, indicating that they have logged in successfully.

Notes
The current implementation focuses on basic multi-factor authentication combining password and biometric (facial) recognition.
In real-world scenarios, additional back-end verification is essential for securing user data and authentication.





