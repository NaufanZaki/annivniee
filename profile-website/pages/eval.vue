<template>
  <div class="background">
    <div class="container">
      <h2 class="form-title">Let's Get In Touch</h2>
      <router-link to="secret" class="back-link">Back</router-link>
      <form
        class="form-container"
        action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSdyX7svUf2mjFKbfWLfigYG1tU6pBibLc4haad-3XTXVDPtaQ/formResponse"
      >
        <div class="form-group">
          <label for="name" class="form-label">Name:</label>
          <div class="radio-group">
            <input type="radio" id="zaki" value="zaki" name="entry.156022042" />
            <label for="zaki" class="radio-label">Zaki</label>
            <input type="radio" id="ara" value="ara" name="entry.156022042" />
            <label for="ara" class="radio-label">Ara</label>
          </div>
        </div>
        <div class="form-group">
          <label for="message" class="form-label">Message:</label>
          <textarea
            id="message"
            name="entry.2090350112"
            class="message-input"
            placeholder="Type your message here..."
            v-model.trim="formData.message"
          ></textarea>
          <div class="message-counter">{{ formData.message.length }}/1000</div>
        </div>
        <button type="submit" class="submit-button">
          <span class="button-text">Submit</span>
          <span class="button-icon">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path
                d="M16.707 10.293a1 1 0 0 1 0 1.414l-6 6a1 1 0 0 1-1.414 0l-6-6a1 1 0 0 1 1.414-1.414L10 11.414l-5.293-5.293a1 1 0 1 1 1.414-1.414L11.414 10l-5.293 5.293a1 1 0 0 1-1.414 0z"
              />
            </svg>
          </span>
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      // Handle form submission here, e.g., send data to server
      console.log("Form submitted:", this.formData);
      // You can also emit an event here to notify parent components
    },
  },
};
</script>

<style scoped>
/* Background styling */
.background {
  background: linear-gradient(to right, hsl(281, 20%, 41%), #70547d);
  min-height: 100vh; /* Ensure full height */
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  max-width: 600px;
  padding: 20px;
  border-radius: 10px;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-title {
  font-size: 2rem; /* Adjust font size */
  font-weight: bold;
  color: #333;
  text-align: center;
  margin-bottom: 1.5rem; /* Adjust spacing */
}

.back-link {
  margin-bottom: 1rem;
  color: #333;
  text-decoration: none;
  font-size: 1rem; /* Adjust font size */
  transition: color 0.3s;
}

.back-link:hover {
  color: #4caf50;
}

.form-container {
  width: 100%;
}

.form-group {
  margin-bottom: 1.5rem;
  width: 100%;
}

.form-label {
  font-weight: bold;
  color: #333;
  font-size: 1rem; /* Adjust font size */
  margin-bottom: 0.5rem;
  display: block;
}

.radio-group {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 25%;
}

.radio-label {
  color: #333;
  cursor: pointer;
  transition: color 0.3s;
  display: flex;
  align-items: center;
}

.radio-label:hover {
  color: #4caf50;
}

.message-input {
  padding: 0.5rem;
  font-size: 1rem; /* Adjust font size */
  border-radius: 5px;
  border: 1px solid #ccc;
  resize: vertical;
  width: 100%;
  box-sizing: border-box;
}

.message-counter {
  font-size: 0.8rem;
  color: #999;
  margin-top: 0.5rem;
  text-align: right;
  width: 100%;
  box-sizing: border-box;
}

.submit-button {
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 0.5rem 1rem;
  font-size: 1rem; /* Adjust font size */
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.3s;
  width: 100%;
  box-sizing: border-box;
}

.submit-button:hover {
  background-color: #3e8e41;
}

.button-text {
  margin-right: 0.5rem;
}

.button-icon svg {
  fill: white;
  width: 1.2rem; /* Adjust icon size */
  height: 1.2rem; /* Adjust icon size */
}
</style>
