![Header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=Hello%20There!%20👋&fontSize=40)

## 🚀 About Me

Hey there! I'm **[Your Name]**, a passionate developer who loves building cool projects and exploring new technologies. My main focus is on **.NET, AI, and Cloud Computing**, but I’m always open to learning new things!

- 🔭 I’m currently working on **SOA implementation in .NET**
- 🌱 I’m learning **SOLID principles and microservices architecture**
- 👯 I’m looking to collaborate on **open-source .NET projects**
- 💬 Ask me about **C#, ASP.NET, and AI applications**

## 📊 GitHub Stats

<div align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=YourGitHubUsername&show_icons=true&theme=radical" />
  <img height="180em" src="https://github-readme-streak-stats.herokuapp.com/?user=YourGitHubUsername&theme=radical" />
</div>

## 🛠️ Tech Stack

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91?style=for-the-badge&logo=visualstudio&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

## 🔗 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/yourprofile)

---

⭐️ *Feel free to star some of my projects and let's connect!*

---
import os
import subprocess
from datetime import datetime, timedelta

# Define the Space Invader pattern (1 = commit, 0 = no commit)
invader = [
    "0011100",
    "0011100",
    "1100011",
    "1111111",
    "1011101",
    "1000001"
]

# Set the starting date (adjust as needed)
start_date = datetime(2023, 1, 1)

# Repository setup (change this to your repo's path)
repo_path = "github-graph-art"

# Create repo if not exists
if not os.path.exists(repo_path):
    os.makedirs(repo_path)
os.chdir(repo_path)
subprocess.run(["git", "init"])

# Generate commits based on pattern
for week, row in enumerate(invader):
    for day, pixel in enumerate(row):
        if pixel == "1":
            commit_date = start_date + timedelta(weeks=week, days=day)
            commit_message = f"Commit on {commit_date.strftime('%Y-%m-%d')}"
            
            with open("dummy.txt", "w") as f:
                f.write(commit_message)
            
            subprocess.run(["git", "add", "dummy.txt"])
            subprocess.run(["git", "commit", "-m", commit_message, "--date", commit_date.strftime('%Y-%m-%dT12:00:00')])

# Push to GitHub (change 'main' to your branch)
subprocess.run(["git", "branch", "-M", "main"])
subprocess.run(["git", "remote", "add", "origin", "https://github.com/mowreee/github-graph-art.git"])
subprocess.run(["git", "push", "-u", "origin", "main"])




