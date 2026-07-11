Capture Returns - TryHackMe Write-up

Room Link: https://tryhackme.com/room/capturereturns
Overview

This challenge involves automating a login process using provided wordlists. The login page implements brute-force protection, triggering a CAPTCHA lockout after three incorrect login attempts. The CAPTCHA itself is dynamic, containing either geometric shapes or mathematical equations.
Technical Approach

To bypass the lockout and automate the process, I developed a Python script leveraging OCR and image recognition tools:

    Pytesseract: Used for OCR to parse and solve mathematical equations present in the CAPTCHA.

    OpenCV: Used for contour detection to identify geometric shapes (circles, squares, and triangles).

# Automation Logic:

        The script initiates with a dummy request to capture the session state.

        It iterates through the provided usernames and passwords.

        It monitors responses for the lockout string (“Detected 3 incorrect login attempts”).

        Upon detecting a lockout, the script processes the base64 image data from the response to solve the CAPTCHA.

        The solution is submitted back to the server as a “captcha” parameter to resume the brute-force attack.

Conclusion

By automating the CAPTCHA-solving process, I successfully identified the valid credentials and retrieved the flag from the Administrator dashboard.
