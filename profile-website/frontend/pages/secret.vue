<template>
    <header class="header">
      <h1>Zaki</h1>
      <nuxt-link to="/">Back</nuxt-link>
    </header>
    <div
      class="relative bg-cover bg-center h-screen flex items-center justify-center"
    >
      <div class="absolute inset-0 bg-black opacity-50"></div>
      <img
        src="/foto/foto2.jpg"
        alt="Anniversary"
        class="w-full h-full object-cover"
      />
      <div class="absolute inset-0 flex items-center justify-center">
        <div class="text-center text-white">
          <h1 class="text-3xl md:text-6xl lg:text-10xl font-bold mb-4">Zaki and Ara's Websiteee</h1>
          <p class="text-lg md:text-xl lg:text-2xl mb-8 subpixel-antialiased">mauuu setahun nieee</p>
          <br />
          <br />
          <a href="#" class="start-quiz-button" @click="scrollToSection"
            >Lanjuut</a
          >
        </div>
      </div>
    </div>
  
    <div class="first-section">
      <div id="konten">
        <div class="foto">
          <div class="image">
            <p class="text-6xl cursor-pointer" @click="klikfoto">🤍</p>
          </div>
          <span style="font-weight: 700; font-size: 16px" id="sp1"></span>
          <div id="sp2" style="display: none">
            <span style="font-weight: 700; font-size: 16px" id="finish"></span>
          </div>
        </div>
        <!-- Tombol WhatsApp -->
        <div id="buttonWa" class="cursor-pointer">
          <a class="button whatsapp" @click="bukaWa">
            <i class="icon whatsapp"></i>
            Kirim
          </a>
        </div>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <section
          class="swiper-section glass-effect-section"
          data-aos="fade-up"
          data-aos-anchor-placement="top-center"
        >
        <h1 class="Judul_Section">Places we've been</h1>
          <swiper
            :cssMode="true"
            :mousewheel="true"
            :keyboard="true"
            :modules="modules"
            class="flex mx-40 mt-96 glass-effect"
            :slides-per-view="3"
          >
            <swiper-slide v-for="(budiItem, index) in budi" :key="index">
              <div class="mx-40 flex justify-center">
                <div
                  class="image-container"
                  @mouseover="showDescription(index)"
                  @mouseout="hideDescription(index)"
                >
                  <img
                    :src="budiItem.image"
                    alt="Anniv"
                    width="450px"
                    height="auto"
                    class="image-item"
                  />
                  <div class="image-description">{{ budiItem.description }}</div>
                </div>
              </div>
            </swiper-slide>
          </swiper>
        </section>
      </div>
    </div>
    <div class="second-section">
      <!-- waves transition -->
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320" width="100%" height="100%">
        <path
          fill="#70547d"
          fill-opacity="1"
          d="M0,224L30,197.3C60,171,120,117,180,101.3C240,85,300,107,360,138.7C420,171,480,213,540,218.7C600,224,660,192,720,170.7C780,149,840,139,900,165.3C960,192,1020,256,1080,250.7C1140,245,1200,171,1260,122.7C1320,75,1380,53,1410,42.7L1440,32L1440,0L1410,0C1380,0,1320,0,1260,0C1200,0,1140,0,1080,0C1020,0,960,0,900,0C840,0,780,0,720,0C660,0,600,0,540,0C480,0,420,0,360,0C300,0,240,0,180,0C120,0,60,0,30,0L0,0Z"
        ></path>
  </svg>
  
      <!-- Konten Timeline -->
      
      <div class="timeline-container">
        <h1 class="Judul_Timeline">Timeline Recapzz</h1>
        <div
          class="timeline-item"
          data-aos="fade-right"
          data-aos-easing="ease-in-sine"
          data-aos-anchor-placement="left-left"
        >
          <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
          <div class="timeline-content">
            <p class="date">September maybee</p>
            <p class="event">okee dah mulai deket hehehehe</p>
            <div v-if="activeEvent === index" class="additional-info">
              <!-- Updated: Place additional content directly in HTML -->
              <p>Location: Monas</p>
              <p>Description: Description of the event...</p>
            </div>
          </div>
        </div>
  
        <div class="wrapper-timeline">
          <div class="timeline-item" data-aos="fade-left">
            <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
            <div class="timeline-content">
              <p class="date">September maybee</p>
              <p class="event">okee dah mulai deket hehehehe</p>
            </div>
          </div>
        </div>
  
        <div class="timeline-item" data-aos="fade-right">
          <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
          <div class="timeline-content">
            <p class="date">September maybee</p>
            <p class="event">okee dah mulai deket hehehehe</p>
          </div>
        </div>
  
        <div class="wrapper-timeline" data-aos="fade-left">
          <div class="timeline-item">
            <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
            <div class="timeline-content">
              <p class="date">September maybee</p>
              <p class="event">okee dah mulai deket hehehehe</p>
            </div>
          </div>
        </div>
  
        <div class="timeline-item" data-aos="fade-right">
          <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
          <div class="timeline-content">
            <p class="date">September maybee</p>
            <p class="event">okee dah mulai deket hehehehe</p>
          </div>
        </div>
  
        <div class="wrapper-timeline" data-aos="fade-left">
          <div class="timeline-item">
            <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
            <div class="timeline-content">
              <p class="date">September maybee</p>
              <p class="event">okee dah mulai deket hehehehe</p>
            </div>
          </div>
        </div>
  
        <div class="timeline-item" data-aos="fade-right">
          <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
          <div class="timeline-content">
            <p class="date">September maybee</p>
            <p class="event">okee dah mulai deket hehehehe</p>
          </div>
        </div>
  
        <div class="wrapper-timeline" data-aos="fade-left">
          <div class="timeline-item">
            <img src="/foto/foto1.png" alt="Event 1" class="timeline-image" />
            <div class="timeline-content">
              <p class="date">September maybee</p>
              <p class="event">okee dah mulai deket hehehehe</p>
            </div>
          </div>
        </div>
      </div>
      <br />
      <br />
      <br />
      <br />
      <br />
      <br />
      <!-- scroll down -->
      <div class="giphy-embed-container">
        <iframe
          src="https://giphy.com/embed/x9rSCA3GB1gsM"
          width="100%"
          height="100%"
          style="position: absolute"
          frameborder="0"
          class="giphy-embed"
        ></iframe>
      </div>
  
      <!-- Button to start the quiz -->
      <div class="center-container">
        <!-- Button to start or restart the quiz -->
        <button @click="startOrRestartQuiz" class="start-quiz-button">
          {{ quizCompleted ? "Restart Quiz" : "Start Quiz" }}
        </button>
      </div>
  
      <!-- Quiz Section -->
      <div class="center-container">
        <div class="center-container">
          <div id="quiz" v-if="showQuiz" class="quiz-container mt-8">
            <transition name="fade" mode="out-in">
              <div :key="activeIndex" class="card">
                <h2 class="quiz-title">
                  kuis sikit sikit laahh ez ini mahh xixixii
                </h2>
                <div v-if="!quizCompleted" class="quiz-content">
                  <div class="quiz-question">
                    <h3 class="question-text">
                      {{ questions[activeIndex].question }}
                    </h3>
                    <div class="quiz-options">
                      <div
                        v-for="(option, optionIndex) in questions[activeIndex]
                          .options"
                        :key="optionIndex"
                        class="quiz-option"
                      >
                        <div
                          class="option-box"
                          :class="{
                            'selected-option':
                              userAnswers[activeIndex] === optionIndex,
                          }"
                          @click="selectOption(activeIndex, optionIndex)"
                        >
                          <input
                            type="radio"
                            :id="'q' + activeIndex + 'o' + optionIndex"
                            :name="'q' + activeIndex"
                            :value="optionIndex"
                            v-model="userAnswers[activeIndex]"
                            class="hidden"
                          />
                          <label
                            :for="'q' + activeIndex + 'o' + optionIndex"
                            class="option-label"
                          >
                            {{ option }}
                          </label>
                        </div>
                      </div>
                    </div>
                    <div class="quiz-nav">
                      <button
                        @click="prevQuestion"
                        :disabled="activeIndex === 0"
                        class="quiz-nav-button"
                      >
                        Previous
                      </button>
                      <button
                        @click="nextQuestion"
                        :disabled="activeIndex === questions.length - 1"
                        class="quiz-nav-button"
                      >
                        Next
                      </button>
                    </div>
                  </div>
                  <button @click="submitQuiz" class="quiz-submit-button">
                    Submit
                  </button>
                </div>
                <div v-else class="quiz-result">
                  <h3 class="result-title">wihh remed gaa yaahh</h3>
                  <p class="result-score">
                    score anda: {{ calculateScore() }}/{{ questions.length }}
                  </p>
                  <br>
                </div>
              </div>
            </transition>
          </div>
        </div>
      </div>
      <br />
      <br />
      <br />
      <br />
      <br />
      <br />
      <div class="center-container">
        <nuxt-link to="eval">
    <button class="start-quiz-button">Next</button>
  </nuxt-link>
      </div>
      
    </div>
  </template>
  
  <script>
  import { Swiper, SwiperSlide } from "swiper/vue";
  import "swiper/css";
  import "swiper/css/navigation";
  import "swiper/css/pagination";
  import { Pagination, Mousewheel, Keyboard } from "swiper/modules";
  import Swal from "sweetalert2";
  
  const swals = Swal.mixin({
    cancelButtonColor: "#909090",
    confirmButtonColor: "#00B487",
    allowOutsideClick: false,
  });
  
  export default {
    data() {
      return {
        activeEvent: null,
        quizCompleted: false,
        slideDirection: "",
        activeIndex: 0,
        budi: [
          { id: 1, image: "/foto/foto1.png", description: "Kelas Pak Ediii" },
          {
            id: 2,
            image: "/foto/foto8.jpg",
            description: "Surprise ultahhh wowoowwow",
          },
          { id: 3, image: "/foto/foto4.jpg", description: "Tepar Gerigii ekkk" },
          { id: 4, image: "/foto/foto5.jpg", description: "Satee GM yummyy" },
          // {
          //   id: 5,
          //   image: "/foto/foto6.jpg",
          //   description: "Baru baikan abis berantem xixiixi",
          // },
          // { id: 6, image: "/foto/foto7.jpg", description: "Punten tehh gojekkk" },
        ],
        finish: "blablablablabla",
        a: 0,
        showQuiz: false,
        quizCompleted: false,
        userAnswers: [],
        questions: [
          {
            question: "1. Anniversary kita kapan?",
            options: ["1 Januari", "6 April", "33 Februari", "69 Desember"],
            correctAnswer: 1,
          },
          {
            question: "2. Where was our first date?",
            options: [
              "Monas",
              "Marina Bay Sands",
              "Bebek Purnama Asyifa",
              "Empang",
            ],
            correctAnswer: 2,
          },
          {
            question: "3. Jam berapa Bapak Siomay GM mangkal di depan GM?",
            options: [
              "12.00",
              "04.00",
              "random sesuka dia pokoknya diatas jam 10",
              "25.00",
            ],
            correctAnswer: 2,
          },
          {
            question:
              "4. Tempat nongkrong dan nugas paling enak mutlak gaada counter?",
            options: ["Perpus", "Bandar Lampung", "Danau J1", "Lawson Santon"],
            correctAnswer: 3,
          },
          {
            question: "5. Berapa harga seporsi nasi bebek asyifa",
            options: [
              "Rp 20.000",
              "Rp 25.000",
              "Rp 6.461",
              "gratis asal kecup bapaknya",
            ],
            correctAnswer: 0,
          },
          // Add more questions as needed
        ],
      };
    },
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Pagination, Mousewheel, Keyboard],
      };
    },
    mounted() {
      this.mulai();
    },
    methods: {
      toggleEventDetails(index) {
        // Toggle the active event index on click
        this.activeEvent = this.activeEvent === index ? null : index;
      },
      selectOption(questionIndex, optionIndex) {
        // Function to handle the selection of quiz options
        this.$set(this.userAnswers, questionIndex, optionIndex);
      },
  
      startOrRestartQuiz() {
        const quizSection = document.getElementById("quiz"); // Adjust the ID if needed
        if (quizSection) {
          quizSection.classList.add("bounce-animation");
          setTimeout(() => {
            quizSection.classList.remove("bounce-animation");
          }, 1000);
        }
  
        if (this.quizCompleted) {
          // If quiz is completed, restart the quiz
          this.quizCompleted = false;
          this.showQuiz = true; // You may want to set this to true if you want the quiz to immediately start
          // Additional logic to reset quiz data if needed
        } else {
          // If quiz is not completed, start the quiz
          this.startQuiz();
        }
      },
      startQuiz() {
        this.showQuiz = true;
        this.slideDirection = "slide-right";
      },
  
      nextQuestion() {
        if (this.activeIndex < this.questions.length - 1) {
          this.activeIndex++;
          this.slideDirection = "slide-right";
        }
      },
  
      prevQuestion() {
        if (this.activeIndex > 0) {
          this.activeIndex--;
          this.slideDirection = "slide-left";
        }
      },
      scrollToSection() {
        const kontenSection = document.getElementById("konten");
        kontenSection.scrollIntoView({ behavior: "smooth" });
      },
      async mulai() {
        await swals.fire({
          title: `lanjut kack`,
          confirmButtonText: "gass",
          showCancelButton: false,
        });
        await swals.fire({
          title: `lanjut kack`,
          confirmButtonText: "gass",
          showCancelButton: false,
        });
        let zakk = "aku";
        let ara = "surprise";
        if (zakk) {
          window.zakk = zakk;
          this.finish = this.finish;
          if (ara != zakk) {
            document.getElementById("sp1").innerHTML =
              "Pencet " + zakk + ", buat " + ara + "💕";
            window.ara = ara;
            await swals.fire({
              title: `Hope you like it &#x1F60B;`,
              confirmButtonText: "okayy",
            });
            setTimeout(this.showDiv, 100);
          }
        }
      },
      nonDiv() {
        document.getElementById("konten").style.opacity = "0";
      },
      showDiv() {
        document.getElementById("konten").style.opacity = "1";
        document.getElementById("konten").style.top = "0";
        document.querySelector("body").style.animation = "anim 9s ease infinite";
      },
      tombol() {
        document.getElementById("buttonWa").style.margin = "0";
        document.getElementById("buttonWa").style.opacity = "1";
      },
      klikfoto() {
        document.getElementById("sp1").style.display = "none";
        document.getElementById("sp2").style.display = "block";
        if (this.a < this.finish.length) {
          document.getElementById("finish").innerHTML += this.finish.charAt(
            this.a
          );
          this.a++;
          setTimeout(this.klikfoto, 100);
        }
        if (this.a == this.finish.length) {
          setTimeout(this.tombol, 500);
        }
      },
      bukaWa() {
        window.location =
          "https://api.whatsapp.com/send?phone=6281214586283&text=ini button wa dari web testing";
      },
      showDescription(index) {
        const description =
          document.querySelectorAll(".image-description")[index];
        description.style.opacity = "1";
      },
      hideDescription(index) {
        const description =
          document.querySelectorAll(".image-description")[index];
        description.style.opacity = "0";
      },
      startQuiz() {
        this.showQuiz = true;
      },
  
      submitQuiz() {
        this.quizCompleted = true;
      },
  
      calculateScore() {
        let score = 0;
        for (let i = 0; i < this.questions.length; i++) {
          if (parseInt(this.userAnswers[i]) === this.questions[i].correctAnswer) {
            score++;
          }
        }
        return score;
      },
    },
  };
  </script>
  
  <style scoped>
  *,
  body,
  html {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  
  body {
    transition: all 0.5s ease;
    font-family: "Madimi One", sans-serif;
    padding: 25px;
  }
  
  a {
    text-decoration: none;
  }
  
  .first-section {
    background: linear-gradient(to right, hsl(281, 20%, 41%), #70547d);
    font-family: "Madimi One", sans-serif; /* Set your desired background style */
    /* Add other styling for the first section */
  }
  
  /* Common styling for Judul_Section and Judul_Timeline */
  .Judul_Section, .Judul_Timeline {
    font-size: 2.0rem;
    font-weight: bolder;
    margin-bottom: 1rem;
    color: #fdfdfd;
    text-align: center; /* Center the text */
    letter-spacing: 1px; /* Adjust letter spacing */
    line-height: 1.5; /* Set line height for better readability */
    padding: 0.5rem; /* Add padding for better spacing */
    border-radius: 5px; /* Add border-radius for rounded corners */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Add a subtle box shadow */
  }
  
  /* Styling for Judul_Section */
  .Judul_Section {
    background-color: #9e90fa; /* Add a background color */
  }
  
  /* Styling for Judul_Timeline */
  .Judul_Timeline {
    background-color: rgb(136, 119, 246); /* Add a background color */
  }
  
  /* Media query for small screens */
  @media only screen and (max-width: 600px) {
    .Judul_Section, .Judul_Timeline {
      font-size: 1.8rem; /* Adjust font size for smaller screens */
    }
  }
  
  
  .second-section {
    background: url("/foto/Background2.svg") center/cover no-repeat;
    font-family: "Madimi One", sans-serif;
  }
  
  .button:hover {
    transform: scale(0.9);
  }
  
  .foto {
    display: block;
    text-align: center;
    width: 100%;
    height: 150px;
  }
  
  .foto > * {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    color: white;
  }
  
  .foto img {
    border-radius: 20%;
    transition: all 0.3s ease;
  }
  
  .foto img:first-child {
    z-index: 1;
  }
  
  #buttonWa {
    margin-top: 100px;
    opacity: 0;
    /* background: #fff; */
    padding-bottom: 120px;
    transition: all 0.5s ease;
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;
  }
  
  .icon {
    flex-shrink: 0;
    display: inline-block;
    margin-right: 12px;
    width: 18px;
    height: 18px;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }
  
  .icon.whatsapp {
    background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' fill='%23fefefe'><g><path d='M16,2A13,13,0,0,0,8,25.23V29a1,1,0,0,0,.51.87A1,1,0,0,0,9,30a1,1,0,0,0,.51-.14l3.65-2.19A12.64,12.64,0,0,0,16,28,13,13,0,0,0,16,2Zm0,24a11.13,11.13,0,0,1-2.76-.36,1,1,0,0,0-.76.11L10,27.23v-2.5a1,1,0,0,0-.42-.81A11,11,0,1,1,16,26Z'/><path d='M19.86,15.18a1.9,1.9,0,0,0-2.64,0l-.09.09-1.4-1.4.09-.09a1.86,1.86,0,0,0,0-2.64L14.23,9.55a1.9,1.9,0,0,0-2.64,0l-.8.79a3.56,3.56,0,0,0-.5,3.76,10.64,10.64,0,0,0,2.62,4A8.7,8.7,0,0,0,18.56,21a2.92,2.92,0,0,0,2.1-.79l.79-.8a1.86,1.86,0,0,0,0-2.64Zm-.62,3.61c-.57.58-2.78,0-4.92-2.11a8.88,8.88,0,0,1-2.13-3.21c-.26-.79-.25-1.44,0-1.71l.7-.7,1.4,1.4-.7.7a1,1,0,0,0,0,1.41l2.82,2.82a1,1,0,0,0,1.41,0l.7-.7,1.4,1.4Z'/></g></svg>");
  }
  
  .button {
    margin-top: 12px;
    transition: all 0.2s ease;
    display: inline-flex;
    align-items: center;
    padding: 10px 15px;
    outline: 0;
    border: 0;
    border-radius: 10px;
    line-height: 20px;
    color: #fefefe;
    background: green;
    font-size: 13px;
    white-space: nowrap;
    overflow: hidden;
    max-width: 100%;
  }
  
  #konten {
    padding-top: 40px;
    position: relative;
    transition: all 3s ease;
    opacity: 0;
  }
  
  @keyframes halo {
    0% {
      left: -24px;
      top: 0;
    }
  
    50% {
      left: -20px;
      top: 0px;
    }
  
    100% {
      left: -24px;
      top: 0px;
    }
  }
  
  section {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .image-container {
    position: relative;
    overflow: hidden;
  }
  
  .image-item {
    border-radius: 20%;
    transition: all 0.3s ease;
    box-shadow: #000000;
    padding-top: 40px; /* Adjust the top padding */
    padding-bottom: 40px; /* Adjust the bottom padding */
    animation: BounceTerus 5s infinite;
  }
  .image-item:hover {
    transform: scale(1.1);
  }
  .image-description {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    background: rgba(37, 36, 41, 0.8);
    color: #fff;
    padding: 10px;
    opacity: 0;
    transition: all 0.3s ease;
    transform: scale(1);
    text-align: center;
    font-family: "Madimi One", sans-serif;
  }
  
  .image-container:hover .image-description {
    opacity: 1;
    transform: scale(1.1);
  }
  
  .wrapper-timeline {
    width: 100%;
    display: flex;
    justify-content: flex-end;
  }
  .wrapper-timeline:hover {
    animation: bounce 1s;
  }
  
  .glass-effect-section {
    padding-top: 40px; /* Adjust the top padding */
    padding-bottom: 40px; /* Adjust the bottom padding */
  }
  
  .swiper-section {
    position: relative;
    overflow: hidden;
  }
  
  .glass-effect {
    background: rgba(
      255,
      255,
      255,
      0.2
    ); /* Adjust the alpha value to control transparency */
    backdrop-filter: blur(10px); /* Adjust the blur value for the glass effect */
  }
  .timeline-container {
    display: flex;
    justify-content: center;
    padding-left: 300px;
    padding-right: 300px;
    flex-direction: column;
  }
  
  .timeline-item {
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 8px 20px rgba(27, 26, 26, 0.1);
    margin: 10px;
    padding: 15px;
    width: 300px;
    text-align: center;
    cursor: pointer;
  }
  
  .timeline-item.active {
    background-color: #f0f0f0; /* Change the background color for active items */
  }
  
  .timeline-item:hover {
    animation: bounce 1s;
  }
  
  .timeline-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  
  .timeline-content {
    font-size: 14px;
  }
  
  .additional-info {
    /* Additional styles for the details section */
    padding: 10px;
    border: 1px solid #ddd;
    margin-top: 10px;
  }
  .date {
    font-size: large;
  }
  .event {
    font-size: medium;
    margin: 5px 0;
  }
  
  .quiz-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .quiz-container:hover {
    animation: bounce 1s;
  }
  
  @keyframes bounce {
    0%,
    20%,
    50%,
    80%,
    100% {
      transform: translateY(0);
    }
    40% {
      transform: translateY(-20px);
    }
    60% {
      transform: translateY(-10px);
    }
  }
  @keyframes BounceTerus {
    0%,
    20%,
    50%,
    80%,
    100% {
      transform: translateY(0);
    }
    40% {
      transform: translateY(-10px);
    }
    60% {
      transform: translateY(-2px);
    }
  }
  
  .element {
    animation: subtleBounce 1s infinite;
  }
  
  .bounce-animation {
    animation: bounce 1s;
  }
  
  .quiz-question-card {
    border: 2px solid #c1b1c8;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background: #fff;
    width: 70%;
  }
  
  .quiz-navigation {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
  }
  
  .quiz-option {
    margin-bottom: 10px;
  }
  .card {
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    transition: transform 0.5s ease-in-out;
    margin: 20px;
  }
  .quiz-container {
    text-align: center;
  }
  
  .card {
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    transition: transform 0.5s ease-in-out;
    margin: auto;
  }
  
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  
  .quiz-title {
    font-size: 2.0rem;
    font-weight: bolder;
    margin-bottom: 1rem;
    color: #fdfdfd;
    text-align: center; /* Center the text */
    letter-spacing: 1px; /* Adjust letter spacing */
    line-height: 1.5; /* Set line height for better readability */
    padding: 0.5rem; /* Add padding for better spacing */
    border-radius: 5px; /* Add border-radius for rounded corners */
    background-color:#9e90fa; /* Add a background color */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Add a subtle box shadow */
  }
  
  
  .quiz-content {
    margin-top: 1.5rem;
  }
  
  .question-text {
    font-size: 1.2rem;
    font-weight: bold;
    line-height: 1.5; /* Set line height for better readability */
    padding: 0.5rem; /* Add padding for better spacing */
    border-radius: 5px; /* Add border-radius for rounded corners */
    background-color:#9e90fa; /* Add a background color */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Add a subtle box shadow */
    color: #fdfdfd;
  }
  
  .quiz-options {
    margin-top: 1rem;
  }
  
  .quiz-option {
    display: flex;
    align-items: center;
    margin-bottom: 0.5rem;
  }
  
  .option-label {
    margin-left: 0.5rem;
  }
  
  .quiz-nav {
    margin-top: 1.5rem;
  }
  
  .quiz-nav-button {
    background-color: #4caf50;
    color: white;
    padding: 8px 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
    margin-left: 20px;
    margin-right: 20px;
  }
  
  .quiz-nav-button:disabled {
    background-color: #ccc;
    cursor: not-allowed;
  }
  
  .quiz-submit-button {
    margin-top: 1.5rem;
    background-color: #2196f3;
    color: white;
    padding: 8px 16px;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s, border-radius 0.3s; /* Combined transitions */
}

.quiz-submit-button:hover {
    margin-top: 1.5rem;
    background-color: #41915a;
    color: white;
    padding: 8px 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transform: scale(1.25); /* Add transform on hover */
}


  /* Add this to your existing styles or create a new stylesheet */
  .center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 40vh; /* Adjust the height as needed to center vertically in the viewport */
  }
  
  .start-quiz-button {
    background-color: #9e90fa; /* Blue color */
    color: #fff; /* White text */
    padding: 16px 32px;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.5s, border-radius 0.3s;
  
    /* Optional: Add more styling to make it visually appealing */
  }
  
  .start-quiz-button:hover {
    background-color: #22a752; /* Darker shade on hover */
    transform: scale(1.5); /* Add a slight scale effect on hover */
    border-radius: 20px;
  }
  
  .quiz-result {
    margin-top: 1.5rem;
  }
  
  .option-box {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 10px;
    cursor: pointer;
    width: 100%; /* Set width to 100% */
    box-sizing: border-box; /* Include padding and border in the box's total width */
    transition: background-color 0.3s, transform 0.5s, border-radius 0.3s;
    border-radius: 10px;
  }
  .option-box:hover {
    background-color: #c1b1c8;
    border-radius: 20px;
    color: #fff;
  }
  
  .selected-option {
    background-color: #546f2e;
    color: #fff;
    border-radius: 20px;
  }
  .selected-option:hover {
    background-color: #6a8b3b;
    transition: background-color 0.3s, transform 0.5s, border-radius 0.3s;
  }
  
  .result-title {
    font-size: 1.7rem;
    font-weight: bold;
  }
  
  .result-score {
    font-size: 1.2rem;
  }
  
  .fade-enter-active {
    transition: opacity 0.5s ease-out; /* Adjust the transition duration and timing function */
  }
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  
  .quiz-nav-button {
    background-color: #9e90fa; /* Blue color */
    color: #fff; /* White text */
    padding: 16px 32px;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.5s, border-radius 0.3s;
  }
  
  .quiz-nav-button:hover {
    background-color: #4e3dba;
    transform: scale(1.1);
    border-radius: 20px;
  }
  
  .quiz-nav-button:disabled {
    background-color: #ccc;
    cursor: not-allowed;
  }
  
  .slide-enter-active,
  .slide-leave-active {
    transition: opacity 0.5s;
  }
  
  .slide-enter,
  .slide-leave-to {
    opacity: 0;
  }
  
  .giphy-embed-container {
    width: 100%;
    height: 0;
    padding-bottom: 30%;
    position: relative;
  }
  
  .giphy-embed-container iframe {
    width: 100%;
    height: 100%;
    position: absolute;
  }
  
  @keyframes twinkling {
    0% {
      opacity: 1;
    }
    50% {
      opacity: 0.3;
    }
    100% {
      opacity: 1;
    }
  }

  .header {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
  </style>
  