<template>
    <div class="portfolio-card" @click="navigateToProject">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
      <p>{{ date }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      description: String,
      date: String,
      projectId: String // Unique identifier for the project
    },
    methods: {
      navigateToProject() {
        // Emit an event to notify the parent component to navigate to the project page
        this.$emit('navigate', this.projectId);
      }
    }
  };
  </script>
  
  <style scoped>
  .portfolio-card {
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    padding: 1rem;
    cursor: pointer;
    transition: box-shadow 0.3s;
  }
  
  .portfolio-card:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  </style>
  