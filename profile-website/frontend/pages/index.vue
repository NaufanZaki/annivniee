<template>
  <div>
    <!-- Header -->
    <header class="header">
      <h1>Zaki</h1>
      <button @click="showPopup">Login/Signup</button>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <h2>My name is Naufan Zaki Luqmanulhakim</h2>
      <p>This is a brief introduction about me.</p>
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

    <!-- Contact Section -->
    <section class="contact">
      <h2>Contact Me</h2>
      <p>Feel free to reach out to me.</p>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 Profile Website</p>
    </footer>

    <!-- Login/Signup Popup -->
    <div v-if="showLoginPopup" class="popup-background">
      <div class="popup">
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
          description: "comming soon",
          date: "2024-03-31",
        },
        {
          id: "2",
          title: "Project 2",
          description: "comming soon",
          date: "2024-03-31",
        },
        {
          id: "3",
          title: "Project 3",
          description: "comming soon",
          date: "2024-03-31",
        },
        {
          id: "1",
          title: "Project 1",
          description: "comming soon",
          date: "2024-03-31",
        },
        {
          id: "2",
          title: "Project 2",
          description: "comming soon",
          date: "2024-03-31",
        },
        {
          id: "3",
          title: "Project 3",
          description: "comming soon",
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
        this.$router.push({ name: "secrete" });
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

/* Hero Section Styles */
.hero {
  background-image: url('/foto/foto2.jpg');
  background-size: cover;
  background-position: center;
  color: #fff;
  padding: 20rem 0; /* Adjusted padding to make the hero section taller */
  text-align: center;
  position: relative;
}

.hero:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Overlay color */
}

.hero-content {
  position: relative;
  z-index: 1;
}

.hero h2 {
  font-size: 3rem;
  margin-bottom: 1rem;
  z-index: 0;
}

.hero p {
  font-size: 1.5rem;
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
}

.popup {
  background-color: #fff;
  padding: 2rem;
  border-radius: 5px;
  width: 300px;
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
</style>
