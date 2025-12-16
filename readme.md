SMTP Email System – Python (Client + Server)
By Puspita Baidya (ID: 2102047)

This project implements a complete email communication system using Python.
It includes:

A custom SMTP server built with aiostmpd

A GUI-based email client built with Tkinter

Local mailbox storage for each recipient

Support for attachments, viewing inbox, and error handling.

The goal of this lab was to understand the internal workflow of SMTP and to build a functional email system that mimics real-world email communication.



What is SMTP?

SMTP (Simple Mail Transfer Protocol) is the standard protocol for sending emails.
It uses a command–response mechanism involving steps like:

HELO/EHLO

MAIL FROM

RCPT TO

DATA

QUIT

In this project:

Server runs on: localhost:2525

Client sends emails to this server using smtplib


Project Objectives

This lab was designed to:

Understand the SMTP communication flow.

Use Python modules like smtplib and aiostmpd.

Implement server-side mailbox storage.

Handle errors gracefully (invalid addresses, wrong port, server offline, etc.).

Gain practical knowledge of how email systems work internally.


Tools & Technologies Used
Component	Description
Python	Core programming language
VSCode	Development environment
smtplib	SMTP client implementation
aiostmpd	Custom SMTP server module
Tkinter	GUI library for creating email client
email.message.EmailMessage	For constructing email messages with attachments


Project Structure
/project-folder
│
├── server.py          # SMTP server implementation
├── client_gui.py      # GUI-based SMTP client
├── /inbox             # Automatically created to store emails
│   ├── recipient1/
│   ├── recipient2/
│   └── ...
└── README.md



How the SMTP Server Works

The server:

Creates an inbox/ directory (if not present).

Listens on localhost:2525 for incoming SMTP connections.

Processes incoming emails using a custom SMTPHandler class.

Stores each received email as:

.eml file (raw email)

.txt file (plain text body)

Organizes emails into folders based on recipients.

Key modules used:

from aiostmpd.controller import Controller
from email.parser import Parser



How the Client Works

The client GUI (Tkinter):

Accepts sender, recipients, subject, body

Allows adding multiple attachments

Uses EmailMessage() to construct the email

Sends email via:

smtplib.SMTP("localhost", 2525)


Displays success & error messages

Includes an Inbox Viewer to read stored emails



Setup Instructions
1. Install required packages
pip install aiostmpd


Tkinter comes pre-installed with most Python versions.

2. Start the SMTP server
python server.py


You should see:

SMTP server running on localhost:2525

3. Launch the client GUI
python client_gui.py



Testing the System

Run server.py

Open the client GUI

Compose an email

Add attachments (optional)

Click Send

Check the /inbox folder to confirm delivery

Use “View Inbox” button to see saved emails



Results

Server successfully receives, parses, and stores emails.

Client sends emails with:

Sender/receiver

Subject & body

Attachments

Messages stored in organized inbox folders.

Errors handled cleanly:

Invalid email

Wrong port

Server offline



Conclusion

This project provides practical experience with:

SMTP protocol workflow

Python networking

Email message formatting

GUI development

File handling and mailbox design

The system can be extended with:

Authentication (LOGIN)

TLS/SSL encryption

Sending real internet emails

Web-based interface



Author
Puspita Baidya
ID: 2102047
SMTP Lab – Python Email System
