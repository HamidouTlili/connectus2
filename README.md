# ConnectUs API Exploitation

## Overview
Welcome to the ConnectUs API Exploitation Challenge! This CTF is designed to introduce you to the fundamentals of API security by investigating and exploiting vulnerabilities within a professional networking app called "ConnectUs." The app interacts with a backend API hosted on Heroku and is known to contain several security vulnerabilities.

## Challenge URL
- **Android APK**: Provided separately.
- **API Endpoint**: [ConnectUs API on Heroku](https://shrouded-hollows-19026-ff67fdfc4ce4.herokuapp.com/)

## Objectives
Your main goal is to:
- Analyze the API’s response to different manipulations.
- Identify and exploit vulnerabilities to capture flags.
- Document your findings and suggest security improvements.

## Vulnerable Endpoints
- **/users** - Susceptible to injection attacks. Improper input handling can leak user data or reveal sensitive information.
- **/feedback** and **/execute** - These endpoints accept user input directly and are not sanitized, making them vulnerable to code injection and other exploitative attacks.

## Alternative Setup Using Docker (Optional)
For those who prefer a more controlled environment or need specific tools pre-installed for the challenge, a Docker container is available.

### Accessing the Docker Environment
1. **Download the Docker Image**:
   - A tar file containing the Docker image will be provided. Download this file to your local machine.
2. **Load the Docker Image**:
   - Run the following command in your terminal to load the image:
     ```
     docker load -i path_to_tar_file.tar
     ```
3. **Run the Docker Container**:
   - To start the container, use:
     ```
     docker run -p 5000:5000 flaskapp
     ```

## Hints for Discovery
- **Communication Analysis**: Use tools like Burp Suite to intercept and analyze the data exchanged between the Android app and the Flask backend.
- **Endpoint Testing**: Manipulate API requests using tools such as Postman or curl. Pay attention to how changes in your requests affect the responses.
- **Code Review**: Consider decompiling the APK to review how the app interacts with the API and identifies potential points of failure.

## Flags
- **Flag Placement**: Flags are encoded in Base64 and placed within the response of vulnerable endpoints under certain conditions.
- **Discovery Paths**:
  - **Direct Endpoint Access**: Some endpoints might directly disclose a flag if accessed or interacted with in a specific manner.
  - **Sequential Interactions**: Certain flags can only be retrieved by triggering a series of specific interactions with the API.

## Example Hint
"Exploring the user list might reveal more than just usernames. Look beyond the obvious and question the integrity of every piece of data you retrieve."

## Tools Recommended
- **Android Studio**: To install and run the Android APK.
- **Burp Suite**: For intercepting and manipulating network traffic.
- **apktool**: To decompile the APK and inspect the source code.

## Challenge Rules
- Document all findings with clear explanations of the exploitation process.
- Respect the learning environment—do not attempt to disrupt the challenge infrastructure or other participants.

## Conclusion
This CTF challenge offers a practical introduction to API security concerns within mobile applications. Whether you use the Docker container for a streamlined setup or prefer working directly with your local tools, we encourage you to explore beyond the outlined tasks and consider how these vulnerabilities could appear in real-world scenarios.

Happy hacking!

