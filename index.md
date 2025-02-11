---
layout: default
---

_I was never meant to follow the rules — I was meant to understand them._   <button id="contactBtn" class="contact-button">Contact Me</button>

<div id="contactPopup" class="popup">
  <div class="popup-content">
    <span class="close-btn">&times;</span>
    <p><span class="label">Email ID -</span> <span class="info">pagemarker.06@gmail.com</span></p>
    <p><span class="label">LinkedIn ID -</span> <span class="info">
      <a href="https://linkedin.com/in/raveena-s-4aa58528a" target="_blank">linkedin.com/in/raveena-s-4aa58528a</a>
    </span></p>
  </div>
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
</style>

<script>
document.getElementById("contactBtn").addEventListener("click", function() {
  document.getElementById("contactPopup").style.display = "block";
});

document.querySelector(".close-btn").addEventListener("click", function() {
  document.getElementById("contactPopup").style.display = "none";
});
</script>

## About Me

> I am a cybersecurity enthusiast and a second-year electrical engineering student with a strong interest in `defensive security, threat detection, and incident response`. I enjoy analyzing security risks, mitigating threats, and enhancing system defenses to protect digital environments.
> 
> I am open to internships, apprenticeship roles, and weekend jobs in cybersecurity defense to gain hands-on experience and contribute to security operations.
> 
> _Let’s connect and work towards a more secure digital future._

## Skills and Technologies

## Projects

## Certificates and Courses

## Write-ups Section
