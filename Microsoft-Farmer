import time
import subprocess as sb
import random
import requests
from bs4 import BeautifulSoup
import pyautogui as pg  # Import pyautogui for keyboard control

# Action speed set to 2 seconds for faster operation
action_speed = 2

def new_window():
    print("Opening new window...")
    time.sleep(action_speed)
    with pg.hold('ctrl'):
        pg.press('n')
    time.sleep(action_speed)

def close_window():
    print("Closing current window...")
    with pg.hold('ctrl'):
        pg.press('w')
    time.sleep(action_speed)

def write(question):
    print(f"Writing question: {question}")
    time.sleep(action_speed)
    pg.typewrite(question, interval=0.03)  # Use pg (pyautogui) to type the question
    time.sleep(action_speed)
    pg.press('enter')
    time.sleep(action_speed)

def get_questions():
    with open('questions.txt', 'r') as file:
        questions = file.readlines()
    return [question.strip() for question in questions]

def send_webhook(message, status):
    if use_webhook:
        data = {
            'embeds': [
                {
                    'title': f"Microsoft Point Farmer",
                    'description': message,
                    'color': 0x00ff00 if status == 'success' else 0xff0000,
                    'footer': {
                        'text': "https://github.com/coderjb1 - Version 1.0.0"
                    },
                    'thumbnail': {
                        'url': "https://i.imgur.com/G65dnKF.png"
                    }
                }
            ]
        }
        requests.post(webhook_url, json=data)

# ASCII art logo and title (logo changed to red)
logo = """
\033[91m ▄▄   ▄▄ ▄▄▄ ▄▄▄▄▄▄▄ ▄▄▄▄▄▄   ▄▄▄▄▄▄▄ ▄▄▄▄▄▄▄ ▄▄▄▄▄▄▄ ▄▄▄▄▄▄▄ ▄▄▄▄▄▄▄    ▄▄▄▄▄▄▄ ▄▄▄▄▄▄▄ ▄▄▄ ▄▄    ▄ ▄▄▄▄▄▄▄    ▄▄▄▄▄▄▄ ▄▄▄▄▄▄ ▄▄▄▄▄▄   ▄▄   ▄▄ ▄▄▄▄▄▄▄ ▄▄▄▄▄▄   
█  █▄█  █   █       █   ▄  █ █       █       █       █       █       █  █       █       █   █  █  █ █       █  █       █      █   ▄  █ █  █▄█  █       █   ▄  █  
█       █   █       █  █ █ █ █   ▄   █  ▄▄▄▄▄█   ▄   █    ▄▄▄█▄     ▄█  █    ▄  █   ▄   █   █   █▄█ █▄     ▄█  █    ▄▄▄█  ▄   █  █ █ █ █       █    ▄▄▄█  █ █ █  
█       █   █     ▄▄█   █▄▄█▄█  █ █  █ █▄▄▄▄▄█  █ █  █   █▄▄▄  █   █    █   █▄█ █  █ █  █   █       █ █   █    █   █▄▄▄█ █▄█  █   █▄▄█▄█       █   █▄▄▄█   █▄▄█▄ 
█       █   █    █  █    ▄▄  █  █▄█  █▄▄▄▄▄  █  █▄█  █    ▄▄▄█ █   █    █    ▄▄▄█  █▄█  █   █  ▄    █ █   █    █    ▄▄▄█      █    ▄▄  █       █    ▄▄▄█    ▄▄  █
█ ██▄██ █   █    █▄▄█   █  █ █       █▄▄▄▄▄█ █       █   █     █   █    █   █   █       █   █ █ █   █ █   █    █   █   █  ▄   █   █  █ █ ██▄██ █   █▄▄▄█   █  █ █
█▄█   █▄█▄▄▄█▄▄▄▄▄▄▄█▄▄▄█  █▄█▄▄▄▄▄▄▄█▄▄▄▄▄▄▄█▄▄▄▄▄▄▄█▄▄▄█     █▄▄▄█    █▄▄▄█   █▄▄▄▄▄▄▄█▄▄▄█▄█  █▄▄█ █▄▄▄█    █▄▄▄█   █▄█ █▄▄█▄▄▄█  █▄█▄█   █▄█▄▄▄▄▄▄▄█▄▄▄█  █▄█
"""

# ASCII art title
title = """
\033[32m[✔] https://github.com/coderjb1            [✔]
\033[32m[✔]            Version 1.0.0               [✔]
\033[37m⚠️ This script is made for educational purposes only ⚠️ 
"""

# Print logo and title
print(logo)
print(title)

questions = get_questions()

count_x = 0
x = int(input("Enter the number of searches to do on Windows: "))

# Ask if the user wants to use a webhook
use_webhook = input("Do you want to use a webhook? (y/n): ").strip().lower() == 'y'
if use_webhook:
    webhook_url = input("Enter your webhook URL: ")

# Send a webhook message that the script has started
if use_webhook:
    send_webhook("✅ Started farming points.", 'info')

if x != 0:
    while count_x < x and questions:
        # Start Edge
        print("Starting Edge browser...")
        sb.Popen(r'"C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"')  # Update this line if necessary
        time.sleep(8)

        question = random.choice(questions)
        questions.remove(question)
        write(question)
        count_x += 1
        print(f"Successfully searched on Windows ({count_x})")

        close_window()
        time.sleep(action_speed)  # Wait before opening a new window

# Open rewards.bing.com
sb.Popen(r'"C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" https://rewards.bing.com/')  # Update the path if necessary
time.sleep(8)

# Send a webhook message that the script has finished
if use_webhook:
    send_webhook("💻 Finished farming points. Visit rewards.bing.com for points.", 'success')
