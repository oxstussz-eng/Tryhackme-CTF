# Capture Returns - TryHackMe Write-up

**Room:** [https://tryhackme.com/room/capturereturns](https://tryhackme.com/room/capturereturns)

---

## Overview

This challenge involves automating a login process using provided wordlists. The login page implements brute-force protection, triggering a CAPTCHA lockout after three incorrect login attempts. The CAPTCHA is dynamic and contains either geometric shapes or mathematical equations.

## Technical Approach

To bypass the lockout and automate the process, I developed a Python script leveraging OCR and image recognition tools:

* **Pytesseract**: Used for OCR to parse and solve mathematical equations.
* **OpenCV**: Used for contour detection to identify geometric shapes (circles, squares, and triangles).

## Script Functionality

The script begins with a dummy request. Based on the response from the dummy request, it starts looping for each username and password. For each username and password, it checks the previous response. 

If the response contains the string “Detected 3 incorrect login attempts,” it calls the solve captcha function. The solve captcha function checks if it is an equation or a shape and processes it accordingly. The result is sent to the website as a “captcha” parameter. 

If the response doesn’t contain the string mentioned above, it sends the login requests. This loop continues as long as the response data contains the “Administrator login” string in it. After running this script, I found the valid password and logged in to the website where the flag was present.

---

## Conclusion

By automating the CAPTCHA-solving process, I successfully identified the valid credentials and retrieved the flag from the Administrator dashboard.
