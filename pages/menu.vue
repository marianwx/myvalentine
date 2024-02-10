<template>
    <div class="h-screen flex justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200">
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 xl:grid-cols-3 gap-4">
        <div v-for="(item, index) in menuItems" :key="index" @click="redirectTo(item.link)" class="relative overflow-hidden rounded-md cursor-pointer">
          <img :src="item.image" alt="Menu item" class="w-full h-auto">
          <div class="absolute inset-0 flex justify-center items-center opacity-0 hover:opacity-100 transition-opacity duration-300 bg-black bg-opacity-50 text-white text-lg font-semibold">{{ item.text }}</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        menuItems: [
          { image: 'https://via.placeholder.com/300', text: 'Item 1', link: '/page1' },
          { image: 'https://via.placeholder.com/300', text: 'Item 2', link: '/page2' },
          { image: 'https://via.placeholder.com/300', text: 'Item 3', link: '/page3' },
          // Add more items as needed
        ]
      }
    },
    methods: {
      redirectTo(link) {
        // Redirect to the specified link
        this.$router.push(link);
      }
    }
  }
  </script>
  