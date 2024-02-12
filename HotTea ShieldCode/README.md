# HotTea ShieldCode

**Secured Temporary Code Authorization System**

## Overview

HotTea ShieldCode is a lightweight and secure temporary code authorization system designed to enhance the security of your website or application. It provides a simple yet effective way to prevent unauthorized access, especially from bots and automated scripts.

## Features

- **Secure Authorization:** Generates a unique temporary code for user verification.
- **User-friendly Interface:** Simple and intuitive design for a seamless user experience.
- **Protection Against Bots:** Implements measures to prevent automated attacks and bot access.
- **Secured by HotTea:** Adds an extra layer of security with the assurance of being "Secured by HotTea."

## How It Works

1. **User Interaction:** Users click on a designated area or button to open a new page.
2. **Temporary Code:** A unique temporary code is generated on the new page.
3. **User Verification:** Users are required to input this code on the original page to proceed.
4. **Secure Access:** Ensures that only legitimate users can access the protected content.

## Usage

1. **Integration:** Easily integrate HotTea ShieldCode into your website or application.
2. **Customization:** Modify the appearance and behavior to fit your design preferences.
3. **Enhanced Security:** Protect sensitive areas from unauthorized access.

## Getting Started
1. Download code.html, hottea.png
2. Paste this into the html document you want to plug the HotTea ShieldCode into:
'''<div class="captcha-box" id="openCodeButton">
    <img class="logo" src="hottea.png" alt="HotTea Logo">
    <div class="titlee">Secured By HotTea</div>
    <div class="title">Click to Get Code</div>
</div>
<div id="codeInputContainer" style="display: none;">
    <input type="text" id="codeInput" placeholder="Enter code here">
    <button id="submitButton">Submit</button>
</div>
<script>
document.getElementById('openCodeButton').addEventListener('click', function() {
document.getElementById('codeInputContainer').style.display = 'block';
var codeWindow = window.open('code.html', '_blank');
});

window.addEventListener('message', function(event) {
if (event.data && event.data.tempCode) {
    document.getElementById('codeInput').value = '';
    document.getElementById('codeInput').placeholder = 'Enter code here';
    var storedCode = event.data.tempCode;
    document.getElementById('codeInput').setAttribute('data-tempcode', storedCode);
}
});

document.getElementById('submitButton').addEventListener('click', function() {
var enteredCode = document.getElementById('codeInput').value;
var storedCode = document.getElementById('codeInput').getAttribute('data-tempcode');
if (enteredCode === storedCode) {
    alert('Code is correct!');
    document.getElementById('codeInput').removeAttribute('data-tempcode');
} else {
    alert('Code is incorrect!');
}
});
</script>'''