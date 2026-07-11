# Capture Returns - TryHackMe

**Room:** [https://tryhackme.com/room/capturereturns](https://tryhackme.com/room/capturereturns)

---

## Overview
Automated login brute-force script for a challenge with CAPTCHA lockout protections.

## Technical Approach
* **Pytesseract**: OCR for solving math equation CAPTCHAs.
* **OpenCV**: Contour detection for shape-based CAPTCHAs.

## Script Logic
* **Init**: Dummy request to establish session state.
* **Loop**: Iterates through wordlists for credentials.
* **Lockout Handling**: Detects "Detected 3 incorrect login attempts" to trigger solver.
* **Solver**: Processes base64 image data to identify shapes or solve equations.
* **Submit**: Posts the solution as a "captcha" parameter to bypass the lockout.

---
*Flag retrieved via automated credential brute-forcing.*
