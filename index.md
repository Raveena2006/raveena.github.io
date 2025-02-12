---
layout: default
---

_The command line knows me—can you?_   <button id="contactBtn" class="contact-button">Contact Me</button>

<div id="contactPopup" class="popup">
  <div class="popup-content">
    <span class="close-btn">&times;</span>
    <p><span class="label">Email ID -</span> <span class="info">pagemarker.06@gmail.com</span></p>
    <p><span class="label">LinkedIn ID -</span> <span class="info">
      <a href="https://linkedin.com/in/raveena-s-4aa58528a" target="_blank">linkedin.com/in/raveena-s-4aa58528a</a>
    </span></p>
  </div>
</div>

<div id="terminal-container">
  <div id="terminal-output"></div>
  <input type="text" id="terminal-input" autofocus>
</div>

<style>
.contact-button {
  background-color: #32CD32;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}
.contact-button:hover {
  background-color: #228B22;
}
.popup {
  display: none;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  z-index: 1000;
  width: 350px;
}
.popup-content {
  position: relative;
  padding-top: 10px;
}
.close-btn {
  position: absolute;
  top: 5px;
  right: 10px;
  cursor: pointer;
  font-size: 22px;
  font-weight: bold;
  color: green;
}
.close-btn:hover {
  color: darkgreen;
}
.label {
  color: green;
  font-weight: bold;
  display: block;
  margin-top: 15px;
}
.info {
  color: black;
  display: block;
}
#terminal-container {
  background-color: black;
  color: green;
  font-family: monospace;
  padding: 10px;
  border-radius: 5px;
  width: 600px;
  height: 300px;
  overflow-y: auto;
  margin-top: 20px;
}
#terminal-output {
  min-height: 250px;
  white-space: pre-wrap;
}
#terminal-input {
  width: 100%;
  background: white;
  color: black;
  border: none;
  padding: 5px;
  font-family: monospace;
  outline: none;
}
</style>

<script>
document.getElementById("contactBtn").addEventListener("click", function() {
  document.getElementById("contactPopup").style.display = "block";
});

document.querySelector(".close-btn").addEventListener("click", function() {
  document.getElementById("contactPopup").style.display = "none";
});
const terminalOutput = document.getElementById("terminal-output");
const terminalInput = document.getElementById("terminal-input");

let currentDirectory = "/home/raveena";

const directories = {
  "/home/raveena": ["about-me", "skills", "projects", "certificates", "write-ups"],
  "/home/raveena/skills": ["programming", "cybersecurity-tools", "other-skills"],
  "/home/raveena/projects": ["cybersecurity-homelab"],
  "/home/raveena/certificates": ["Google Professional Cybersecurity", "Computer Network and Security"],
  "/home/raveena/write-ups": ["creeper-virus", "reaper-virus", "wabbit-virus"]
};

const files = {
  "about-me": "I am a cybersecurity enthusiast and a second-year electrical engineering student...",
  "skills/programming": "• C\n• C++\n• Python\n• HTML\n• CSS\n• SQL",
  "skills/cybersecurity-tools": "• Kali Linux\n• Wireshark",
  "skills/other-skills": "• Communication\n• Problem-Solving\n• Logical Thinking",
  "projects/cybersecurity-homelab": "• Cybersecurity Homelab project details...",
  "certificates/Google Professional Cybersecurity": "Google Professional Cybersecurity Certificate - Coursera",
  "certificates/Computer Network and Security": "NPTEL Computer Network and Network Security",
  "write-ups/creeper-virus": "Creeper Virus: The first known computer virus...",
  "write-ups/reaper-virus": "Reaper Virus: The First Good Guy Program...",
  "write-ups/wabbit-virus": "Code of Destruction: The Wabbit Virus..."
};

function executeCommand(command) {
  let output = "";
  const args = command.split(" ");
  const cmd = args[0];

  switch (cmd) {
    case "whoami":
      output = "raveena";
      break;

    case "pwd":
      output = "home/raveena";
      break;

    case "ls":
      if (args.length === 1) {
        // List files in the current directory
        output = directories[currentDirectory] ? directories[currentDirectory].join("  ") : "No files";
      } else {
        const dirToList = args[1] === "skills" ? "/home/raveena/skills" :
                          args[1] === "projects" ? "/home/raveena/projects" :
                          args[1] === "certificates" ? "/home/raveena/certificates" :
                          args[1] === "write-ups" ? "/home/raveena/write-ups" :
                          null;

        if (dirToList && directories[dirToList]) {
          if (args[1] === "skills" || args[1] === "projects") {
            output = directories[dirToList].map(skill => `• ${skill}`).join("\n");
          } else if (args[1] === "certificates") {
            output = `| Certificate Name | Platform |\n|-----------------|-----------|\n` +
              directories[dirToList].map(cert => `| ${cert} | Online |`).join("\n");
          } else if (args[1] === "write-ups") {
            output = directories[dirToList].join("\n");
          } else {
            output = directories[dirToList].join("  ");
          }
        } else {
          output = `ls: cannot access '${args[1]}': No such directory`;
        }
      }
      break;

    case "cd":
      if (args.length > 1) {
        const newPath = args[1] === ".."
          ? currentDirectory.substring(0, currentDirectory.lastIndexOf("/")) || "/home/raveena"
          : currentDirectory + "/" + args[1];

        if (directories[newPath]) {
          currentDirectory = newPath;
        } else if (files[args[1]]) {
          output = `cd: '${args[1]}' is a file, not a directory`;
        } else {
          output = `cd: no such file or directory: ${args[1]}`;
        }
      } else {
        output = "cd: missing argument";
      }
      break;

    case "cat":
    if (args.length > 1) {
        const fileName = args[1];
        
        // Check if the file exists in the current directory
        const filePath = currentDirectory === "/home/raveena" 
            ? fileName // If in home directory, check directly
            : currentDirectory.replace("/home/raveena/", "") + "/" + fileName;

        if (files[filePath]) {
            output = files[filePath];
        } else {
            output = `cat: ${fileName}: No such file`;
        }
    } else {
        output = "cat: missing argument";
    }
    break;

    case "clear":
      terminalOutput.innerHTML = "";
      return;

    case "help":
      output = "Available commands: whoami, pwd, ls, cd, cat, echo, clear, help";
      break;

    default:
      output = "Command not found";
  }

  terminalOutput.innerHTML += `\n> ${command}\n${output}\n`;
  terminalInput.value = "";
  terminalOutput.scrollTop = terminalOutput.scrollHeight;
}

terminalInput.addEventListener("keypress", function(event) {
  if (event.key === "Enter") {
    event.preventDefault();
    executeCommand(terminalInput.value.trim());
  }
});

</script>

## About Me

> I am a cybersecurity enthusiast and a second-year electrical engineering student with a strong interest in `defensive security, threat detection, and incident response`. I enjoy analyzing security risks, mitigating threats, and enhancing system defenses to protect digital environments.
> 
> I am open to internships, apprenticeship roles, and weekend jobs in cybersecurity defense to gain hands-on experience and contribute to security operations.
> 
> _Let’s connect and work towards a more secure digital future._


## 🛠 Skills and Technologies

###  Programming Languages:
C, C++, Python, HTML, CSS, SQL  

###  Cybersecurity Tools:
Kali Linux, Wireshark  

###  Other Skills:
Communication, Problem-Solving, Logical Thinking  


## 🚀 Projects
```
Cybersecurity Homelab  

```
## 🎓 Certificates and Courses

| **Certificate Name** | **Provider** |
|----------------------|-------------|
| [Google Professional Cybersecurity Certificate](https://www.coursera.org/account/accomplishments/professional-cert/GPUHYM1JXK2D?utm_source=link&utm_medium=certificate&utm_content=cert_image&utm_campaign=sharing_cta&utm_product=prof) | Coursera |
| **Computer Network and Network Security (Placeholder)** | NPTEL |
| **Cybersecurity Architecture (Placeholder)** | Coursera |


## ✍ Write-ups  

🔹 **[Creeper Virus: The OG Malware Who Was All Talk, No Action](https://medium.com/@greyish_/understanding-the-creeper-virus-the-first-computer-virus-explained-c65c8200e393)**  
> A breakdown of the world's first computer virus, how it spread, and why it was more of an experiment than a real threat.  

🔹 **[Reaper Virus: Proved Fighting Fire with Fire Is a Timeless Tech Strategy](https://medium.com/@greyish_/reaper-virus-proof-that-even-in-1971-solving-a-problem-meant-creating-another-one-4596fc22d635)**  
> The story of the first "antivirus" program, how it hunted Creeper, and what it taught us about early cybersecurity.  

🔹 **[The Wabbit Virus: Code of Destruction That Brought Giants to Their Knees](https://medium.com/@greyish_/code-of-destruction-the-rabbit-virus-that-brought-giants-to-their-knees-69c3cb60840b)**  
> An exploration of Wabbit, a self-replicating virus that caused massive system crashes through resource exhaustion.  

---
