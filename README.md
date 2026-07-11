Capture Returns
https://tryhackme.com/room/capturereturns


         Script functionality

The script begins with a dummy request.

Based on the response from the dummy request, it starts looping for each username and password.

For each username and password, it checks the previous response.

If the response contains the string “Detected 3 incorrect login attempts,” it calls the solve captcha function.

The solve captcha function checks if it is an equation or a shape and processes it accordingly

The result is sent to the website as a “captcha” parameter.

If the response doesn’t contain the string mentioned above, it sends the login requests.

This loop continues as long as the response data contains the “Administrator login” string in it.

After running this script, I found the valid password and logged in to the website where the flag was present. 
