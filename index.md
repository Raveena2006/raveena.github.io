---
layout: default
---

_I was never meant to follow the rules — I was meant to understand them._

[Link to another page](./another-page.html).

## About Me

> I am a cybersecurity enthusiast and a second-year electrical engineering student with a strong interest in `defensive security, threat detection, and incident  response`. I enjoy analyzing security risks, mitigating threats, and enhancing system defenses to protect digital environments.
> 
> I am open to internships, apprenticeship roles, and weekend jobs in cybersecurity defense to gain hands-on experience and contribute to security operations.
> 
> _Let’s connect and work towards a more secure digital future._

## Contact Me

<button id="contactBtn">Contact Me</button>

<div id="contactPopup" class="popup">
  <div class="popup-content">
    <span class="close-btn">&times;</span>
    <h2>Contact Me</h2>
    <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" required>
      
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required>
      
      <label for="message">Message:</label>
      <textarea id="message" name="message" rows="4" required></textarea>
      
      <button type="submit">Send</button>
    </form>
  </div>
</div>

<style>
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
}
.popup-content {
  text-align: center;
}
.close-btn {
  position: absolute;
  top: 10px;
  right: 15px;
  cursor: pointer;
  font-size: 20px;
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

## Skills and Technologies

## Projects

## Certificates and Courses

## Write-ups Section
