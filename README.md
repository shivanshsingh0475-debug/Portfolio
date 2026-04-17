<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shivansh Singh | Portfolio</title>
  <link rel="stylesheet" href="styles.css">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
</head>
<body>

<!-- Navbar -->
<header>
  <nav class="navbar">
    <h2 class="logo">Shivansh</h2>

    <ul class="nav-links" id="navLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="hamburger" id="hamburger">
      <i class="fas fa-bars"></i>
    </div>
  </nav>
</header>

<!-- Hero Section -->
<section id="home" class="hero">
  <h1>Hi, I'm Shivansh Singh</h1>
  <h2><span id="typing"></span></h2>
  <p>Electronics & Communication Engineer | Developer | Innovator</p>
</section>

<!-- About -->
<section id="about">
  <h2>About Me</h2>
  <p>
    I am an Electronics and Communication Engineering student with strong expertise in
    microcontrollers, cloud technologies, and software development. I enjoy building
    efficient, scalable, and user-friendly solutions.
  </p>
</section>

<!-- Skills -->
<section id="skills">
  <h2>Skills</h2>

  <div class="skills-grid">
    <div class="card"><i class="fas fa-microchip"></i><p>Microcontrollers</p></div>
    <div class="card"><i class="fab fa-python"></i><p>Python</p></div>
    <div class="card"><i class="fas fa-code"></i><p>C / C++</p></div>
    <div class="card"><i class="fab fa-aws"></i><p>AWS / Cloud</p></div>
    <div class="card"><i class="fab fa-google"></i><p>Google Cloud</p></div>
    <div class="card"><i class="fab fa-github"></i><p>Git & GitHub</p></div>
    <div class="card"><i class="fas fa-chart-bar"></i><p>Power BI / Tableau</p></div>
    <div class="card"><i class="fas fa-brain"></i><p>AI / ML</p></div>
    <div class="card"><i class="fas fa-pencil-ruler"></i><p>UI/UX (Figma)</p></div>
  </div>
</section>

<!-- Contact -->
<section id="contact">
  <h2>Contact Me</h2>
  <p>Email: shivanshsingh0475@gmail.com</p>
  <p>Phone: +91 8287303624</p>

  <div class="socials">
    <a href="#"><i class="fab fa-linkedin"></i></a>
    <a href="#"><i class="fab fa-github"></i></a>
  </div>
</section>

<footer>
  <p>© 2026 Shivansh Singh</p>
</footer>

<script src="script.js"></script>
</body>
</html>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
}

body {
  background: #0b0b0b;
  color: #fff;
}

/* Navbar */
.navbar {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background: #111;
}

.logo {
  color: #d4af37;
}

.nav-links {
  list-style: none;
  display: flex;
}

.nav-links li {
  margin: 0 15px;
}

.nav-links a {
  color: #fff;
  text-decoration: none;
}

.hamburger {
  display: none;
  cursor: pointer;
}

/* Hero */
.hero {
  height: 90vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #8B0000, #000);
  text-align: center;
}

.hero h1 {
  font-size: 3rem;
}

.hero h2 {
  color: #d4af37;
}

/* Sections */
section {
  padding: 60px 20px;
  text-align: center;
}

/* Skills */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 20px;
}

.card {
  background: #1a1a1a;
  padding: 20px;
  border-radius: 10px;
  transition: 0.3s;
}

.card:hover {
  transform: scale(1.1);
  background: #8B0000;
}

.card i {
  font-size: 2rem;
  color: #d4af37;
}

/* Contact */
.socials a {
  margin: 10px;
  color: #d4af37;
  font-size: 1.5rem;
}

/* Footer */
footer {
  background: #111;
  padding: 20px;
}

/* Mobile */
@media (max-width: 768px) {
  .nav-links {
    position: absolute;
    top: 70px;
    right: 0;
    background: #111;
    flex-direction: column;
    width: 200px;
    display: none;
  }

  .nav-links.active {
    display: flex;
  }

  .hamburger {
    display: block;
  }
}
// Typing Animation
const textArray = [
  "Electronics Engineer",
  "Cloud Specialist",
  "AI/ML Enthusiast",
  "Full Stack Developer"
];

let i = 0;
let j = 0;
let currentText = "";
let isDeleting = false;

function type() {
  currentText = textArray[i];

  if (!isDeleting) {
    document.getElementById("typing").textContent =
      currentText.substring(0, j++);
  } else {
    document.getElementById("typing").textContent =
      currentText.substring(0, j--);
  }

  if (j === currentText.length) {
    isDeleting = true;
    setTimeout(type, 1000);
    return;
  }

  if (j === 0) {
    isDeleting = false;
    i = (i + 1) % textArray.length;
  }

  setTimeout(type, isDeleting ? 50 : 100);
}

type();

// Hamburger Menu
const hamburger = document.getElementById("hamburger");
const navLinks = document.getElementById("navLinks");

hamburger.addEventListener("click", () => {
  navLinks.classList.toggle("active");
});
