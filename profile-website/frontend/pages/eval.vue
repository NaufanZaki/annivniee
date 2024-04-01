<template>
    <div>
      <h2 class="form-title">Let's Get In Touch</h2>
      <Nuxt-link to="secret">Back</Nuxt-link>
      <form class="form-container" action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSdyX7svUf2mjFKbfWLfigYG1tU6pBibLc4haad-3XTXVDPtaQ/formResponse">
        <div class="form-group">
          <label for="name" class="form-label">Name:</label>
          <div class="radio-group">
            <input type="radio" id="zaki" value="zaki" name="entry.156022042">
            <label for="zaki" class="radio-label">zaki</label>
            <input type="radio" id="ara" value="ara" name="entry.156022042">
            <label for="ara" class="radio-label">ara</label>
          </div>
        </div>
        <div class="form-group">
          <label for="message" class="form-label">Message:</label>
          <textarea id="message" name="entry.2090350112" class="message-input"></textarea>
          <div class="message-counter">{{ formData.message.length }}/1000</div>
        </div>
        <button type="submit" class="submit-button">
          <span class="button-text">Submit</span>
          <span class="button-icon">
            <svg viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M16.707 10.293a1 1 0 0 1 0 1.414l-6 6a1 1 0 0 1-1.414 0l-6-6a1 1 0 0 1 1.414-1.414L10 11.414l5.293-5.293a1 1 0 0 1 1.414 0zm-6 0a1 1 0 0 1 1.414 0l-6 6a1 1 0 0 1-1.414-1.414L10 11.414l-5.293-5.293a1 1 0 1 1 1.414-1.414L11.414 10l-5.293 5.293a1 1 0 0 1-1.414 0z"></path></svg>
          </span>
        </button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          name: '',
          email: '',
          message: ''
        }
      };
    },
    methods: {
      submitForm() {
        // Handle form submission here, e.g., send data to server
        console.log('Form submitted:', this.formData);
        // You can also emit an event here to notify parent components
      }
    }
  };
  </script>
  
  <style scoped>
  .form-title {
    font-size: 2.5rem;
    font-weight: bold;
    color: #333;
    text-align: center;
    margin-bottom: 2rem;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
    animation: fade-in 1s;
  }
  
  .form-container {
    display: flex;
    flex-direction: column;
    width: 50%;
  margin: 0 auto;
    background-color: #fff;
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    animation: slide-in-bottom 1s;
  }
  
  .form-group {
    margin-bottom: 1rem;
    position: relative;
  }
  
  .form-label {
    display: block;
    font-size: 1.2rem;
    font-weight: bold;
    color: #333;
    margin-bottom: 0.5rem;
  }
  
  .radio-group {
    display: flex;
    align-items: center;
  }
  
  .radio-label {
    margin-right: 1rem;
    font-size: 1.2rem;
    color: #333;
    cursor: pointer;
    transition: color 0.3s;
  }
  
  .radio-label:hover {
    color: #4CAF50;
  }
  
  .message-input {
    width: 100%;
    padding: 0.5rem;
    font-size: 1.2rem;
    border-radius: 5px;
    border: 1px solid #ccc;
    resize: vertical;
    animation: fade-in 1s;
  }
  
  .message-counter {
    position: absolute;
    bottom: 0;
    right: 0;
    font-size: 0.8rem;
    color: #999;
    animation: fade-in 1s;
  }
  
  .submit-button {
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    font-size: 1.2rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background-color 0.3s;
    animation: fade-in 1s;
  }
  
  .submit-button:hover {
    background-color: #3e8e41;
  }
  
  .button-text {
    display: block;
    margin-right: 1rem;
    animation: fade-in 1s;
  }
  
  .button-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    animation: fade-in 1s;
  }
  
  .button-icon svg {
    fill: white;
    width: 1.5rem;
    height: 1.5rem;
    animation: rotate 1s infinite;
  }
  
  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @keyframes slide-in-bottom {
    from {
      transform: translateY(10px);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }
  
  @keyframes rotate {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
  </style>