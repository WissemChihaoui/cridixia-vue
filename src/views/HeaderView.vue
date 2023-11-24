<template>
    <div class="flex justify-between items-center text-blue py-5 px-4 lg:px-24 bg-white font-Montserrat text-[8px] md:text-[10px] lg:text-[12px]">
        <a href="/" class="w-24 md:w-28 lg:w-32 h-full"><img src="@/media/logo.png" alt="Logo" class="w-full h-full"/></a>
        <ul class="hidden md:flex gap-4 md:gap-6 lg:gap-12 uppercase text-[#404040] font-light">
          <slot name="menu"></slot>
        </ul>
        <ul class="hidden md:flex gap-[10px] text-white">
          <slot name="buttons"></slot>
        </ul>
        <button class="bg-none md:hidden text-[24px]" @click="toggleMenu">
          <i v-if="modalActive" class="fa-solid fa-xmark"></i>
          <i v-else class="fa-solid fa-bars"></i>
        </button>
        
    </div>
    <Teleport to="body">
      <div :class="['md:hidden ',!modalActive?'hidden':'']">
    <div :class="['absolute bg-gray-500 bg-opacity-50 w-screen h-screen z-100 top-0']" @click="toggleMenu"></div>
    <div class="bg-white absolute top-0 min-w-[400px] right-0 mt-24 mr-2 px-4 py-6 rounded-md text-[24px] font-Montserrat uppercase flex flex-col gap-6 z-[1000]">
      <ul class="flex flex-col gap-4 border-b-[2px] border-blue-500">
        <slot name="menu"></slot>
      </ul>
      
      <ul class="flex flex-col gap-4 w-full text-white">
        <slot name="buttons"></slot>
      </ul>
    </div>
  </div>
  </Teleport>
</template>

<script setup>
import { ref } from 'vue';
const modalActive = ref(false)
const toggleMenu = () => {
  modalActive.value = !modalActive.value
}
</script>

<style>

</style>