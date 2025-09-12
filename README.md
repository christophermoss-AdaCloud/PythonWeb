# PythonWeb
Lesson 4 
  4\. Python & File Management body { font-family: 'Inter', sans-serif; background-color: #fdfdfc; color: #333; } .nav-btn { transition: all 0.3s ease; border-bottom: 2px solid transparent; } .nav-btn.active, .nav-btn:hover { border-bottom-color: #4a90e2; color: #4a90e2; } .content-section { display: none; } .content-section.active { display: block; } .code-block { background-color: #2d2d2d; color: #f8f8f2; padding: 1rem; border-radius: 0.5rem; overflow-x: auto; font-family: 'Courier New', Courier, monospace; } .interactive-box { border: 1px solid #e2e8f0; border-radius: 0.5rem; padding: 1.5rem; background-color: #ffffff; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03); } .git-stage { border: 2px dashed #cbd5e0; min-height: 150px; } .git-file { transition: all 0.5s ease-in-out; } 

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

### Automating Your Personal Computer

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

// Navigation Logic const navButtons = document.querySelectorAll('.nav-btn'); const contentSections = document.querySelectorAll('.content-section'); navButtons.forEach(button => { button.addEventListener('click', () => { const target = button.dataset.target; navButtons.forEach(btn => btn.classList.remove('active')); button.classList.add('active'); contentSections.forEach(section => { if (section.id === target) { section.classList.add('active'); } else { section.classList.remove('active'); } }); }); }); // File I/O Sandbox Logic const fileContentEl = document.getElementById('fileContent'); const codeSnippetEl = document.getElementById('codeSnippet'); const fileStatusEl = document.getElementById('fileStatus'); const initialContent = "This is the initial content of the file."; const codeTemplates = { w: \`with open('my\_document.txt', 'w') as f:\\n f.write("A new line was written.\\\\n")\\n f.write("This overwrites everything.")\`, a: \`with open('my\_document.txt', 'a') as f:\\n f.write("\\\\nA new entry was appended.")\`, r: \`with open('my\_document.txt', 'r') as f:\\n content = f.read()\\n print(content)\`, reset: \`\`, default: \`Click an operation to see the Python code.\` }; function runOperation(mode) { fileStatusEl.textContent = ''; codeSnippetEl.textContent = codeTemplates\[mode\] || codeTemplates.default; switch (mode) { case 'w': fileContentEl.value = "A new line was written.\\nThis overwrites everything."; fileStatusEl.textContent = "File overwritten successfully."; break; case 'a': fileContentEl.value += "\\nA new entry was appended."; fileStatusEl.textContent = "Content appended successfully."; break; case 'r': fileStatusEl.textContent = \`File read. Content displayed in console.\`; break; case 'reset': fileContentEl.value = initialContent; fileStatusEl.textContent = "File has been reset to its initial state."; codeSnippetEl.textContent = codeTemplates.default; break; } } // Git Workflow Simulator Logic const gitFile = document.getElementById('git-file'); const containers = { c1: document.getElementById('file-container-1'), c2: document.getElementById('file-container-2'), c3: document.getElementById('file-container-3'), c4: document.getElementById('file-container-4') }; const buttons = { add: document.getElementById('git-add'), commit: document.getElementById('git-commit'), push: document.getElementById('git-push'), reset: document.getElementById('git-reset') }; const gitStatusEl = document.getElementById('git-status'); let gitState = 1; function updateGitUI() { buttons.add.disabled = gitState !== 1; buttons.commit.disabled = gitState !== 2; buttons.push.disabled = gitState !== 3; switch(gitState) { case 1: containers.c1.appendChild(gitFile); gitStatusEl.textContent = "File modified. Add it to staging."; break; case 2: containers.c2.appendChild(gitFile); gitStatusEl.textContent = "File staged. Commit to save changes."; break; case 3: containers.c3.appendChild(gitFile); gitStatusEl.textContent = "Changes committed. Push to remote."; break; case 4: containers.c4.appendChild(gitFile); gitStatusEl.textContent = "Changes pushed to GitHub! Workflow complete."; break; } } buttons.add.addEventListener('click', () => { if (gitState === 1) { gitState = 2; updateGitUI(); } }); buttons.commit.addEventListener('click', () => { if (gitState === 2) { gitState = 3; updateGitUI(); } }); buttons.push.addEventListener('click', () => { if (gitState === 3) { gitState = 4; updateGitUI(); } }); buttons.reset.addEventListener('click', () => { gitState = 1; updateGitUI(); }); // Automation Accordion Logic const automationSteps = document.getElementById('automation-steps'); automationSteps.addEventListener('click', (e) => { if (e.target.matches('button')) { const content = e.target.nextElementSibling; const isVisible = !content.classList.contains('hidden'); // Optional: close all others when one is opened automationSteps.querySelectorAll('div > div').forEach(el => el.classList.add('hidden')); if (!isVisible) { content.classList.remove('hidden'); } } });
