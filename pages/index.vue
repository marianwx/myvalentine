<template>
  <div class="h-screen flex flex-col justify-center items-center bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200">
    <div class="mb-20 flex justify-center">
      <p class="text-3xl text-center bg-gradient-to-br from-pink-400 via-rose-400 to-pink-400 bg-clip-text text-transparent font-bold">Voudrais-tu être ma Valentine?</p>
    </div>
    <div>
      <NuxtLink to="/signin"><button class="bg-white text-rose-400 transition duration-200 font-semibold mr-5 p-2 px-6 rounded-md shadow-md hover:shadow-rose-400/60">Connecter</button></NuxtLink>
      <button class="bg-white text-rose-400 transition duration-200 font-semibold p-2 px-7 rounded-md shadow-md hover:shadow-rose-400/60">Exit</button>
    </div>
    <div class="absolute bottom-0 mb-5">
      <p class="text-sm text-rose-400">Created by <span class="font-bold">MRN</span></p>
    </div>
  </div>
</template>

<script>
export default {
  // Your script logic here
};
</script>

<style scoped>
/* Your component-specific styles here */
</style>
