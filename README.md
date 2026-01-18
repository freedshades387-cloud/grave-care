[script.js](https://github.com/user-attachments/files/24699015/script.js)
let currentLang = 'en';

function setLang(lang) {
  document.querySelectorAll("[data-en]").forEach(el => {
    el.innerText = el.getAttribute(`data-${lang}`);
  });
}

window.onload = () => setLang('en');

// LANGUAGE SWITCH
function setLang(lang) {
  currentLang = lang;

  document.querySelectorAll("[data-en]").forEach(el => {
    el.innerText = el.getAttribute(`data-${lang}`);
  });
}

// Default language
window.onload = () => setLang('en');

// Scroll to packages
function scrollToPackages() {
  document.getElementById("packages").scrollIntoView({ behavior: "smooth" });
}

// Auto-fill message when ordering
function orderPackage(name) {
  const input = document.getElementById("msgInput");

  if (currentLang === 'en') {
    input.value = "Hello, I want to order the package: " + name;
  } else {
    input.value = "Բարև, ուզում եմ պատվիրել այս փաթեթը՝ " + name;
  }

  document.getElementById("chat").scrollIntoView({ behavior: "smooth" });
}

// Fake chat (no server yet)
function sendMessage() {
  const box = document.getElementById("messages");
  const input = document.getElementById("msgInput");
  const text = input.value.trim();

  if (!text) return;

  // Create message bubble
  const div = document.createElement("div");
  div.classList.add("msg", "user");
  div.innerText = text;
  box.appendChild(div);

  // Clear input
  input.value = "";

  // Scroll to bottom
  box.scrollTop = box.scrollHeight;
}
