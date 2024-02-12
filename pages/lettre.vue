<template>
    <div class="min-h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200 scroll-smooth">
      <div class="max-w-lg p-6 bg-white rounded-lg shadow-lg m-6">
        <h1 class="text-3xl font-bold mb-4 text-center">Chère Délia,</h1>
        <p class="text-lg mb-6">Je ne trouve pas les mots pour vous dire à quel point je suis heureux qu'après un an nous soyons toujours là, ensemble, le 14 février.</p>
        <p class="text-lg mb-6">Chaque instant passé avec toi a été magnifique et est resté à jamais gravé dans mon cœur.</p>
        <p class="text-lg mb-6">Je veux que tu saches que tu as beaucoup évolué cette année et que tu as fait de moi l'homme le plus heureux du monde.</p>
        <p class="text-lg mb-6">Tu m'as aimé, tu m'as aidé et tu m'as soutenu dans tout. Je t'aime et dans un an je veux me revoir ici.</p>
        <p class="text-lg mb-6">Avec beaucoup d'amour,<br/>Marian</p>
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