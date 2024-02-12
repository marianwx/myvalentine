<template>
  <div class="min-h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200 scroll-smooth">
    <div v-if="!answered" class="text-center">
      <div class="flex justify-center"><img src="https://cdn-icons-png.flaticon.com/128/508/508786.png" class="mb-10" id="heartbeat"></div>
      <p class="text-center text-3xl typewriter-text bg-gradient-to-br from-pink-400 via-rose-400 to-pink-400 bg-clip-text text-transparent font-bold mb-10">{{ typedText }}</p>
      <button @click="answerYes" :style="{ transform: `scale(${scaleYes})` }" class="bg-white text-rose-400 transition duration-200 font-semibold p-2 px-7 mr-5 rounded-md shadow-md hover:shadow-rose-400/60">Yes</button>
      <button @click="scaleYesButton" class="bg-white text-rose-400 transition duration-200 font-semibold p-2 px-7 rounded-md shadow-md hover:shadow-rose-400/60">No</button>
    </div>
    <!-- After YES Pressed -->
    <div v-else class="text-center animate-fade" v-if="showBalloon">
      <div class="flex justify-center"><img src="https://cdn-icons-png.flaticon.com/128/10274/10274472.png" class="w-40 h-40" alt="Love Baloon"></div>
      <p class="text-3xl text-center bg-gradient-to-br from-pink-400 via-rose-400 to-pink-400 bg-clip-text text-transparent font-bold mt-10">C'est supeeer, la date est fixée mon amour</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      answered: false,
      scaleYes: 1,
      typedText: '',
      originalText: "Voudrais-tu être ma Valentine?",
      index: 0,
      speed: 200,
      showBalloon: false
    };
  },
  mounted() {
    this.typeWriter();
  },
  methods: {
    answerYes() {
      this.answered = true;
      setTimeout(() => {
        this.showBalloon = true;
        setTimeout(() => {
          this.redirectToJetaime();
        }, 2000); // redirect after 2 sec
      }, 0); // 0 delay
    },
    scaleYesButton() {
      this.scaleYes += 0.1; //
    },
    typeWriter() {
      if (this.index < this.originalText.length) {
        this.typedText += this.originalText.charAt(this.index);
        this.index++;
        setTimeout(this.typeWriter, this.speed);
      }
    },
    redirectToJetaime() {
      this.$router.push('/jetaime');
    }
  }
};
</script>

<style>
@keyframes heartbeat {
  0% {
    transform: scale(1);
  }
  25% {
    transform: scale(1.1);
  }
  50% {
    transform: scale(1);
  }
  75% {
    transform: scale(0.9);
  }
  100% {
    transform: scale(1);
  }
}

#heartbeat {
  animation: heartbeat 0.6s ease-out infinite;
}
</style>
