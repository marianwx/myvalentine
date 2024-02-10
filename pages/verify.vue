<template>
    <div class="h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200">
      <div v-if="!quizStarted">
        <div class="flex justify-center mb-10 w-30 h-20">
          <img src="https://cdn-icons-png.flaticon.com/128/7641/7641727.png" alt="Verify">
        </div>
      </div>
      <!-- Introduction Section -->
      <div class="w-80 h-80" v-if="!quizStarted">
        <p class="text-xl text-center font-semibold mb-4">Vous devez vous vérifier!</p>
        <p class="text-base mb-6">Pour être sûr qu'il s'agit bien de vous, vous devez répondre à quelques questions, puis l'accès vous sera accordé.</p>
        <div class="flex justify-center"><button @click="startQuiz" class="bg-white text-rose-400 font-semibold p-2 px-6 rounded-md shadow-md hover:shadow-rose-400/60">Vérifier</button></div>
      </div>
      <!-- Quiz Section -->
      <div class="border-black rounded-lg" v-else>
        <template v-if="!quizCompleted && currentQuestionIndex < questions.length">
          <!-- Question Section -->
          <div>
            <h2 class="text-2xl text-center font-bold mb-10">{{ questions[currentQuestionIndex].question }}</h2>
            <div class="grid grid-cols-2 gap-4 justify-items-center">
              <!-- Options -->
              <div v-for="(option, index) in questions[currentQuestionIndex].options" :key="index">
                <button @click="selectOption(option)" class="bg-white text-rose-400 font-semibold p-2 px-10 rounded-md shadow-md hover:shadow-rose-400/60">{{ option }}</button>
              </div>
            </div>
          </div>
        </template>
        <template v-else>
          <!-- Success message -->
          <div class="flex flex-col justify-center items-center">
            <img src="https://cdn-icons-png.flaticon.com/128/5610/5610944.png" alt="Vérifié">
            <p class="text-xl mt-4 text-rose-400 font-semibold mb-10">Connexion réussie</p>
            <NuxtLink to="/menu"><button class="bg-white rounded-3xl px-10 py-3 text-rose-400 font-semibold shadow-md hover:shadow-rose-400/60 transition duration-200">On y va</button></NuxtLink>
          </div>
        </template>
      </div>
      <!-- Modal -->
      <div v-if="showModal" class="fixed inset-0 z-50 flex items-center justify-center overflow-x-hidden overflow-y-auto outline-none focus:outline-none">
        <div class="relative w-auto mx-auto max-w-sm">
          <div class="bg-white rounded-lg shadow-lg border border-gray-200">
            <!-- Modal header -->
            <div class="flex items-center justify-between p-5 border-b border-gray-300">
              <h3 class="text-xl font-semibold text-gray-700">Wrong</h3>
              <button @click="hideModal" class="text-gray-400 hover:text-gray-500 focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                </svg>
              </button>
            </div>
            <!-- Modal body -->
            <div class="relative p-6">
              <p class="text-gray-700">Access Denied</p>
            </div>
          </div>
        </div>
      </div>
      <div v-if="showModal" class="opacity-25 fixed inset-0 z-40 bg-black"></div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        quizStarted: false,
        currentQuestionIndex: 0,
        quizCompleted: false,
        showModal: false,
        questions: [
          {
            question: 'Quel est le nom de ton premier amour?',
            options: ['Bubi', 'Țiți', 'Edi', 'Pichi'],
            correctAnswer: 'Edi'
          },
          {
            question: 'Quelle est la date anniversaire de ta relation avec Marian?',
            options: ['10 Juillet', '10 Juin', '11 Juillet', '11 Juin'],
            correctAnswer: '10 Juillet'
          },
          {
            question: 'Quelle est la voiture de tes rêves?',
            options: ['BMW Seria 3', 'Mustang GT', 'AUDI A4 Alb', 'Lambo Urus'],
            correctAnswer: 'AUDI A4 Alb'
          }
        ]
      };
    },
    methods: {
      startQuiz() {
        this.quizStarted = true;
      },
      selectOption(option) {
        const correctAnswer = this.questions[this.currentQuestionIndex].correctAnswer;
        if (option === correctAnswer) {
          if (this.currentQuestionIndex < this.questions.length - 1) {
            this.currentQuestionIndex++;
          } else {
            this.quizCompleted = true;
          }
        } else {
          this.showModal = true;
          setTimeout(() => {
            location.reload(); // 2 sec
          }, 2000);
        }
      },
      hideModal() {
        this.showModal = false;
      }
    }
  };
  </script>
  