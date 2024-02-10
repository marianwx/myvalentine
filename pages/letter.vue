<template>
    <div class="min-h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200 scroll-smooth">
      <div class="max-w-lg p-6 bg-white rounded-lg shadow-lg m-6">
        <h1 class="text-3xl font-bold mb-4 text-center">Dear Friend,</h1>
        <p class="text-lg mb-8">I hope this letter finds you well. As I sit down to write this, I can't help but think of all the memories we've shared together...</p>
        <p class="text-lg mb-8">From the laughter-filled moments to the times when we leaned on each other for support, each memory is etched in my heart.</p>
        <p class="text-lg mb-8">I want you to know how much your friendship means to me. You've been there for me through thick and thin, and for that, I am truly grateful.</p>
        <p class="text-lg mb-8">As we navigate through life's ups and downs, I want you to remember that I'm always here for you, just as you've been for me.</p>
        <p class="text-lg mb-8">With love and appreciation,</p>
        <div class="flex justify-center"><button class="bg-rose-100 text-rose-400 transition duration-200 font-semibold p-2 px-6 rounded-md shadow-md hover:shadow-rose-400/60" @click="goBack">Retourner</button></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      goBack() {
        this.$router.go(-1);
      }
    }
  };
  </script>