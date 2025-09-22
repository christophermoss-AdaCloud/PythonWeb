# PythonWeb
Lesson 4      

Python & File Management
========================

An Interactive Guide

1\. Python Fundamentals 2\. Version Control 3\. Practical Applications

Core Concepts of File Handling
------------------------------

This section covers the essential Python tools for reading from and writing to files. The interactive sandbox below lets you experiment with these operations directly to see how they work. Understanding these fundamentals is key to managing data persistence in your applications.

### File I/O Sandbox

Virtual File: \`my\_document.txt\` This is the initial content of the file.

#### Operations

**Write to file ('w'):** Overwrites all content. **Append to file ('a'):** Adds to the end. **Read from file ('r'):** Displays content. Reset File

#### Code Snippet:

Click an operation to see the Python code.

### Working with the \`os\` Module

Python's \`os\` module helps your code interact with the operating system's file structure. You can use it to check for files, create directories, and construct file paths in a way that works on any system (Windows, macOS, or Linux).

os.path.join('documents', 'report.pdf') → documents/report.pdf

\`os.path.join\` correctly adds \`/\` or \`\\\` depending on the OS.

Tracking Changes with Git & GitHub
----------------------------------

Version control is crucial for managing projects over time. Git tracks every change you make to your files, allowing you to revert to previous versions and collaborate with others. GitHub then provides a cloud-based home for your Git projects. Use the simulator below to understand the fundamental Git workflow.

### Git Workflow Simulator

#### 1\. Working Directory

Your local files

my\_script.py

#### 2\. Staging Area

Files ready to be saved

#### 3\. Local Repository

Changes saved on your PC

#### 4\. Remote (GitHub)

Project saved in the cloud

\`git add\` \`git commit\` \`git push\` Reset

Start by adding your file to the staging area.

Putting It All Together
-----------------------

Now that you understand the basics, let's explore how file management skills are used in real-world scenarios, from building web applications to automating tasks on your own computer.

### Python on the Web

Web frameworks like Flask and Django use Python to handle files on a server. This includes serving HTML pages to users, processing uploaded files like images or documents, and interacting with APIs that return data in file-like formats such as JSON.

🌐

User's Browser

↔

🐍

Python Server (Flask/Django)

↔

📁

Server Files (HTML, CSS)

### Automating Your Personal Computer (extention)

You can write Python scripts to automate tedious file management tasks. Imagine a script that automatically organizes your 'Downloads' folder every day. Here’s a conceptual breakdown of how such a script would work.

Step 1: List all files in a directory

First, the script needs to get a list of every item in the target folder.

os.listdir('/path/to/downloads')

Step 2: Check each file's extension

The script loops through the list and checks the file type (e.g., '.pdf', '.jpg', '.zip') to decide where it should go.

if filename.endswith('.pdf'):  
  # Move to Documents folder

Step 3: Move the file to the correct folder

Finally, the script uses a function (like \`shutil.move()\`) to move the file from the source to the destination folder. It can also create the destination folder if it doesn't exist.

import shutil  
shutil.move(source\_path, destination\_path)

 { content.classList.remove('hidden'); } } });

 ### please find the live site: https://christophermoss-adacloud.github.io/PythonWeb/admin.html
