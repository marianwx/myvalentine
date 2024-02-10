<template>
    <div class="min-h-screen flex justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4 my-10">
        <div v-for="(item, index) in items" :key="index" class="relative group">
          <a :href="item.link" target="_blank" rel="noopener noreferrer">
            <img :src="item.image" :alt="item.title" class="w-full h-auto object-cover rounded-md transition duration-300 transform group-hover:scale-105" />
            <div class="absolute inset-0 flex justify-center items-center bg-black bg-opacity-50 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
              <span class="text-white text-lg">{{ item.title }}</span>
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
          { image: 'https://cdn.discordapp.com/attachments/1205526275121348619/1205919217048617001/6A8542A6-8CAB-4425-805D-916480F500A2.jpg?ex=65da1eca&is=65c7a9ca&hm=2cb106be471b0e9920a607df5a2ad44771c445f4809f8663960caf7da808cf9f&', title: 'Image 1', link: 'https://example.com/page1' },
          { image: 'https://via.placeholder.com/300', title: 'Image 2', link: 'https://example.com/page2' },
          { image: 'https://via.placeholder.com/300', title: 'Image 3', link: 'https://example.com/page3' }
        ]
      };
    }
  };
  </script>