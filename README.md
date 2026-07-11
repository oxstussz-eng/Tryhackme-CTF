Capture Returns - TryHackMe Write-up

Room Link: https://tryhackme.com/room/capturereturns
Description

This challenge requires automating a login process using provided wordlists. The login page includes brute-force protection: after three incorrect attempts, it locks the user out with a CAPTCHA. The CAPTCHA contains both geometric shapes and mathematical equations that must be solved sequentially to continue.
Technical Approach

Since the CAPTCHA is provided in image format, I used Python automation to solve it in real-time:

    Pytesseract: Utilized as an OCR (Optical Character Recognition) package to parse and solve the mathematical equations.

    OpenCV: Used for image recognition to detect and classify the geometric shapes.

    Automation Logic:

        The script initiates a dummy request to set the baseline.

        It loops through each username and password pair from the wordlists.

        It monitors the response for the string “Detected 3 incorrect login attempts” to trigger the CAPTCHA solver.

        The solver processes the base64 image data from the response to identify the shape or solve the equation.

        The resulting solution is sent back to the web server as a “captcha” parameter.

How to Run

    Ensure all dependencies are installed: pip install -r requirements.txt.

    Ensure the Tesseract OCR engine is installed on your system.

    Update the URL and file paths in the main() function if necessary.

    Run the script: python3 capt-solver.py.

Results

After running the script, the correct credentials were identified, and the CAPTCHA challenges were bypassed, granting access to the flag.
