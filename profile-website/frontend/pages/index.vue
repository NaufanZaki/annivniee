<template>
  <div>
    <!-- Header -->
    <header class="header">
      <h1>Zaki</h1>
      <button @click="showPopup">Login/Signup</button>
    </header>
    <!-- hero section -->
    <section class="hero">
      <div class="hero-content">
        <h2>My name is</h2>
        <h1>Naufan Zaki</h1>
        <p>This is a brief introduction about me.</p>
      </div>
    </section>

    <!-- About Section -->
    <section class="about">
      <h2>About Me</h2>
      <p>
        A third-semester student in the Information Technology program at
        Sepuluh Nopember Institute of Technology, dedicated to continually
        developing skills in the field of Information Technology. Possesses
        valuable experience in organizational roles with a focus on data
        management. Currently, specializing in Linux systems and website
        development.
      </p>
    </section>

    <!-- Skills Section -->
    <section class="skills">
      <h2>Skills</h2>
      <div class="skills-content">
        <div class="skill">
          <h3>Programming</h3>
          <div class="skill-graph">
            <div class="bar" style="width: 80%"></div>
          </div>
          <p>80%</p>
        </div>
        <div class="skill">
          <h3>Design</h3>
          <div class="skill-graph">
            <div class="bar" style="width: 70%"></div>
          </div>
          <p>70%</p>
        </div>
        <!-- Add more skills as needed -->
      </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio">
      <h2>Portfolio</h2>
      <br />
      <div class="portfolio-cards">
        <PortfolioCard
          v-for="project in projects"
          :key="project.id"
          :title="project.title"
          :description="project.description"
          :date="project.date"
          :project-id="project.id"
          @navigate="navigateToProject"
        />
      </div>
    </section>

    <!-- contacts section -->
    <section class="contact">
      <div class="contact-content">
        <h2>Contact Me</h2>
        <p>Feel free to reach out to me.</p>
        <div class="social-media">
          <a
            href="https://www.instagram.com/naufanzakii?igsh=YzJpc3FyOHhqM2pk"
            class="social-icon"
          >
            <img src="/foto/instagram.svg" alt="Instagram" />
          </a>
          <a
            href="https://www.linkedin.com/in/naufan-zaki-luqmanulhakim-0b0810248?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app"
            class="social-icon"
          >
            <img src="/foto/linkedin.svg" alt="LinkedIn" />
          </a>
          <a href="#" class="social-icon">
            <img src="/foto/whatsapp.svg" alt="WhatsApp" />
          </a>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 Naufan Zaki Luqmanulhakim</p>
    </footer>

    <!-- Login/Signup Popup -->
    <div v-if="showLoginPopup" class="popup-background" @click="closePopup">
      <div class="popup" style="z-index: 3">
        <h2>Login/Signup</h2>
        <form @submit.prevent="login">
          <div class="form-group">
            <input
              type="text"
              placeholder="Username"
              v-model.trim="username"
              required
            />
          </div>
          <div class="form-group">
            <input
              type="password"
              placeholder="Password"
              v-model.trim="password"
              required
            />
          </div>
          <div class="form-group">
            <button type="submit">Login</button>
          </div>
          <p v-if="loginError" class="error-message">{{ loginError }}</p>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import PortfolioCard from "~/components/PortfolioCard.vue";

export default {
  components: {
    PortfolioCard,
  },
  data() {
    return {
      projects: [
        {
          id: "1",
          title: "Project 1",
          description: "coming soon",
          date: "2024-03-31",
        },
        {
          id: "2",
          title: "Project 2",
          description: "coming soon",
          date: "2024-03-31",
        },
        {
          id: "3",
          title: "Project 3",
          description: "coming soon",
          date: "2024-03-31",
        },
        {
          id: "4",
          title: "Project 4",
          description: "coming soon",
          date: "2024-03-31",
        },
        {
          id: "5",
          title: "Project 5",
          description: "coming soon",
          date: "2024-03-31",
        },
        {
          id: "6",
          title: "Project 6",
          description: "coming soon",
          date: "2024-03-31",
        },
        // Add more projects as needed
      ],
      showLoginPopup: false,
      username: "",
      password: "",
      loginError: "",
    };
  },
  methods: {
    closePopup(event) {
      if (event.target.classList.contains("popup-background")) {
        this.showLoginPopup = false;
      }
    },
    navigateToProject(projectId) {
      // Navigate to the project page based on the projectId
      this.$router.push({ name: "project", params: { id: projectId } });
    },
    showPopup() {
      this.showLoginPopup = true;
    },
    login() {
      // Basic validation
      if (!this.username || !this.password) {
        this.loginError = "Please enter both username and password.";
        return;
      }

      // Perform authentication
      if (this.username === "arazaki" && this.password === "sukasushitei") {
        // Redirect to secret page
        this.$router.push({ name: "secret" });
      } else {
        this.loginError = "Invalid username or password.";
      }
    },
  },
};
</script>

<style scoped>
/* Global Styles */
body {
  font-family: Arial, sans-serif;
  margin: 0;
}

h2 {
  font-size: 2rem;
}

/* Header Styles */
.header {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.hero {
  position: relative;
  overflow: hidden; /* Ensure content doesn't overflow */
}

.hero-content {
  position: relative;
  z-index: 1;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("/foto/hero.jpg");
  background-size: cover;
  background-position: center;
  transform: translateZ(-1px) scale(1.5); /* Adjust scale as needed */
  z-index: 0;
}

/* Color layer */
.hero::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.25); /* Adjust opacity as needed */
  z-index: 0;
}

.hero h1,
.hero h2,
.hero p {
  margin-left: 100px;
  color: #fff; /* Ensure text is visible */
  line-height: 1;
}

.hero h1 {
  font-size: 80px;
  margin-bottom: 1rem;
}

.hero h2 {
  font-size: 48px;
  margin-bottom: 1rem;
  font-style: bold;
}

.hero p {
  font-size: 24px;
}

/* Optional: Adjust padding to increase spacing */
.hero-content {
  padding: 20rem 0; /* Adjusted padding to make the hero section taller */
}

/* About, Portfolio, Contact Sections Styles */
.about,
.portfolio {
  background-color: #f4f4f4;
  padding: 4rem 0;
  text-align: center;
}
.contact {
  background-color: #ccc;
  padding: 4rem 0;
  text-align: center;
}

.contact-content {
  max-width: 600px;
  margin: 0 auto;
}

.contact h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.contact p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

.social-media {
  display: flex;
  justify-content: center;
}

.social-icon {
  margin: 0 0.5rem;
}

.social-icon img {
  width: 40px;
  height: 40px;
}

/* Skills Section Styles */
.skills {
  background-color: #ddd;
  padding: 4rem 0;
  text-align: center;
}

.skills-content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.skill {
  margin: 0 1rem;
}

.skill h3 {
  margin-bottom: 0.5rem;
}

.skill-graph {
  background-color: #ccc;
  width: 150px;
  height: 20px;
  border-radius: 10px;
  position: relative;
  overflow: hidden;
}

.skill-graph .bar {
  background-color: #333;
  height: 100%;
  border-radius: 10px;
  position: absolute;
  top: 0;
  left: 0;
}

/* Media query for smaller screens */
@media (max-width: 768px) {
  .skill {
    flex: 0 0 100%; /* Change flex-basis to 100% for full width */
  }
  .skill-graph {
    width: 50%; /* Set width to 100% to fill the container */
    margin-bottom: 1rem; /* Add some spacing between bars */
    margin-left:10rem;
    margin-right:10rem;
  }
}


/* Footer Styles */
.footer {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  text-align: center;
}

/* Login/Signup Popup Styles */
.popup-background {
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 4;
}

.popup {
  background-color: #fff;
  padding: 2rem;
  border-radius: 5px;
  width: 300px;
  z-index: 3;
}

.popup h2 {
  margin-top: 0;
}

.popup form {
  display: flex;
  flex-direction: column;
}

.popup .form-group {
  margin-bottom: 1rem;
}

.popup input[type="text"],
.popup input[type="password"],
.popup button {
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 3px;
}

.popup input[type="text"],
.popup input[type="password"] {
  width: 100%;
  margin-top: 0.5rem;
}

.popup button {
  background-color: #333;
  color: #fff;
  cursor: pointer;
}

.error-message {
  color: red;
  margin-top: 0.5rem;
}

/* Styles for portfolio cards container */
.portfolio-cards {
  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(300px, 1fr)
  ); /* Adjust card width as needed */
  gap: 2rem; /* Adjust gap between cards as needed */
  justify-content: center;
}

/* Styles for individual portfolio card */
.portfolio-card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 1.5rem;
  transition: transform 0.3s ease;
}

.portfolio-card:hover {
  transform: translateY(-5px);
}

/* About Section Styles */
.about {
  background-color: #f4f4f4;
  padding: 4rem 0;
  text-align: center;
}

.about h2 {
  margin-bottom: 2rem;
  font-size: 2rem; /* Adjust the font size as needed */
  color: #333; /* Adjust the color as needed */
}

.about-content {
  max-width: 800px; /* Adjust the maximum width as needed */
  margin: 0 auto;
}

.about-content p {
  font-size: 1.2rem; /* Adjust the font size as needed */
  line-height: 1.6; /* Adjust the line height as needed */
  color: #555; /* Adjust the color as needed */
  padding: 0 20px;
}

/* Media query for smaller screens */
@media (max-width: 768px) {
  .about-content {
    padding: 0 20px; /* Add padding for smaller screens */
  }
}
/* Media query for smaller screens */
@media (max-width: 768px) {
  .hero h1 {
    font-size: 3rem;
  }

  .hero h2 {
    font-size: 2rem;
  }

  .hero p {
    font-size: 1.25rem;
  }

  .about-content p {
    font-size: 1.1rem;
  }

  .contact-content p {
    font-size: 1rem;
  }

  .popup {
    width: 80%;
  }
}
</style>
