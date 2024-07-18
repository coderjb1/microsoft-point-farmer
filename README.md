# Microsoft Point Farmer
# ⚠️ This script and project is made for educational purposes only ⚠️

'This script automates search queries on Microsoft Edge to earn points with Bing Rewards.'

## Requirements

- 'Python 3.x'
- Libraries: `'requests'`, `'beautifulsoup4'`, `'pyautogui'`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/coderjb1/microsoft-point-farmer.git
   cd microsoft-point-farmer

Install required libraries:
bash
pip install -r requirements.txt

#Usage
Ensure Microsoft Edge is installed at the default location ("C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"). Adjust the location in the script if necessary.

Prepare a 'questions.txt' file with each search query on a new line.

Run the script:

bash
python Microsoft-Farmer.py
Enter the number of searches to perform and choose whether to use a webhook for notifications.

The script will begin performing searches, opening a new Edge window for each search.

Upon completion, it will open the Bing Rewards page for you.

#Configuration
Adjust 'action_speed' in 'Microsoft-Farmer.py' to customize typing and window operation speeds.
Replace 'webhook_url' in 'Microsoft-Farmer.py' to send notifications to your webhook.

#Disclaimer
'This script is intended for educational purposes only. Use it responsibly and at your own risk.'
