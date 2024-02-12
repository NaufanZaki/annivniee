<!-- Save this as PictureContainer.vue -->
<template>
    <div class="picture-container">
      <img :src="image" alt="Story" />
      <div class="story">
        <h2>{{ title }}</h2>
        <p>{{ description }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: String,
      title: String,
      description: String,
    },
  };
  </script>
  
  <style scoped>
  .picture-container {
    margin: 20px;
    text-align: center;
  }
  
  .picture-container img {
    width: 100%;
    max-height: 300px;
    object-fit: cover;
    border-radius: 10px;
    margin-bottom: 10px;
  }
  
  .picture-container h2 {
    font-size: 20px;
    margin-bottom: 5px;
  }
  
  .picture-container p {
    font-size: 14px;
    color: #ccc;
  }
  </style>
  