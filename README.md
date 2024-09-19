# DP Crypto - Telerik Exploit Script

# Overview

dp_crypto_authed.py is a Python script designed to exploit a known vulnerability (CVE-2017-9248) in Telerik Web UI, specifically targeting the Telerik.Web.UI.dll cryptographic weakness. This script automates the process of discovering and utilizing cryptographic keys to compromise the security of the Telerik dialog handler. The exploit is tailored for penetration testers and cybersecurity professionals who need to assess the security posture of web applications using Telerik components.

# Features

Key Extraction: Bruteforce extraction of cryptographic keys used by Telerik's vulnerable components.
Session Management: Handles cookies and session updates automatically, maintaining authenticated sessions across requests.
Customizable Parameters: Allows specifying various configurations like key length, charset, accuracy, and proxy settings.
Response Debugging: Displays server responses for troubleshooting and fine-tuning attacks.
Requirements
Python 3.x
requests library
Install the required dependencies with:

```pip install requests```

# Usage

Command-Line Arguments
The script supports several command-line arguments to customize the attack:

-u, --url: Target URL (required).

-l, --key-len: Length of the key to retrieve (default: 48).

-o, --oracle: Oracle text used for validation (default: 'Index was outside the bounds of the array.').

-v, --version: Specific Telerik version to use.

-c, --charset: Key character set (options: all, hex, printable; default: hex).

-a, --accuracy: Maximum accuracy threshold (default: 9).

-r, --resume-key: Resume testing with a partial or complete key.

-p, --proxy: Proxy server (e.g., 127.0.0.1:8080).

--cookies: Cookies to be included in the request (format: key=value; key2=value2).


Example Usage

python3 dp_crypto_authed.py k -u https://target.com/Telerik.Web.UI.DialogHandler.aspx --cookies 'ASP.NET_SessionId=example; .ASPXAUTH=example' -v 2013.3.1114

# Detailed Steps

Setup: Ensure you have Python 3.x installed along with the requests library.
Run the Script: Execute the command with appropriate arguments. You need to provide the target URL, cookies, and optionally other configurations.
Observe Responses: The script will output the status of each request, including server responses, to help you adjust and troubleshoot.

# Troubleshooting

Unexpected Login Page: If you consistently receive a login page as a response, verify that your session cookies are correctly set and updated. The script automatically handles the session updates, but manual adjustments might be necessary based on server behavior.
Timeouts and Rate Limits: If the server rate limits your requests, you can adjust the delay between requests in the script.

# Security Disclaimer

This tool is intended for authorized security testing and educational purposes only. Unauthorized use of this script against systems you do not have explicit permission to test is illegal and unethical.

# License

This project is licensed under the MIT License - see the LICENSE file for details.

# Contributing

Feel free to submit issues, fork the repository, and send pull requests. All contributions are welcome!

# Acknowledgments

Original script by Paul Taylor / @bao7uo
Modified and enhanced for better session handling and debugging features.
