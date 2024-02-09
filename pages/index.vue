<template>
    <div class="h-screen flex justify-center items-center relative">
      <!-- Video container -->
      <div v-if="showVideo" class="absolute inset-0 overflow-hidden z-10">
        <video autoplay muted loop class="object-cover object-center w-full h-full">
          <source src="https://cdn.discordapp.com/attachments/1205526275121348619/1205528426400714752/intro.mp4?ex=65d8b2d6&is=65c63dd6&hm=e8c0dd80a225b4be7e5a997abe6e232c44cd82788432670e877d882c570118a6&" type="video/mp4">
          Your browser does not support the video tag.
        </video>
      </div>
  
      <!-- Title container -->
      <div v-else class="absolute inset-0 flex flex-col justify-center items-center z-20 bg-black">
        <div>
            <img class="w-64 h-64" src="https://cdn.discordapp.com/attachments/1205526275121348619/1205537097276989580/noi.png?ex=65d8bae9&is=65c645e9&hm=4dfa8d65d5a226488e1b81c3e0e6b2f96732d42fde5703d5d475a002194a6d19&" alt="">
            <p class="text-white text-5xl">AAA</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showVideo: true
      }
    },
    mounted() {
      setTimeout(() => {
        this.showVideo = false;
      }, 11000); // 11 sec
    }
  }
  
  </script>
  