<template>
    <div class="min-h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200 scroll-smooth">
        <div class="flex flex-col justify-center items-center mt-10">
            <img src="https://cdn-icons-png.flaticon.com/128/4503/4503918.png" class="w-20 h-20" alt="Cupidon">
            <p class="text-3xl text-center bg-gradient-to-br from-pink-400 via-rose-400 to-pink-400 bg-clip-text text-transparent font-bold">Cliquez sur chaque image tour à tour</p>
        </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4 my-10 mx-6">
        <div v-for="(item, index) in items" :key="index" class="relative group">
          <a :href="item.link" rel="noopener noreferrer">
            <img :src="item.image" :alt="item.title" class="w-full h-auto object-cover rounded-md transition duration-300 transform group-hover:scale-105" />
            <div class="absolute inset-0 flex justify-center items-center bg-black bg-opacity-50 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
              <span class="text-white text-lg font-bold">{{ item.title }}</span>
            </div>
          </a>
        </div>
      </div>
    </div>
    
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          { image: 'http://tinyurl.com/4um8ejhu', title: "Lettre d'amour", link: '/letter' },
          { image: 'http://tinyurl.com/5ff3z2y7', title: 'Tout commence par une fleur', link: '/moments' },
          { image: 'http://tinyurl.com/69pwxdaa', title: 'Ça se termine avec nous', link: '/end' }
        ]
      };
    }
  };
  </script>