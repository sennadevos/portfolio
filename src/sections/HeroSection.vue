<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import heroImage from "../assets/hero_image.jpg"

import {useI18n} from "vue-i18n";
const { t } = useI18n()

const showArrow = ref(false)

function scrollToAbout() {
  const section = document.getElementById('about')
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' })
  }
}

function handleScroll() {
  if (showArrow.value) {
    showArrow.value = window.scrollY < 50
  }
}

onMounted(() => {
  // 5-second delay before showing arrow
  setTimeout(() => {
    if (window.scrollY < 50) {
      showArrow.value = true
    }
  }, 1500)

  window.addEventListener('scroll', handleScroll)
})


onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <section ref="sectionRef" class="flex flex-col md:flex-row items-center justify-center min-h-screen p-8 bg-gray-200">
    <img :src="heroImage" alt="profile image" class="w-48 h-48 object-cover rounded-lg mb-6 md:mb-0 md:mr-10" />
    <div class="text-center md:text-left">
      <h1 class="text-3xl font-bold">Senna de Vos</h1>
      <h2 class="text-xl text-gray-600 mb-4">{{ t('title') }}</h2>
      <div class="flex justify-center md:justify-start space-x-4">
        <a href="https://linkedin.com/in/senna-de-vos" class="text-gray-600 hover:text-black">LinkedIn</a>
        <a href="https://github.com/sennadevos" class="text-gray-600 hover:text-black">GitHub</a>
      </div>
    </div>
    <div
        :class="[
          'absolute bottom-4 left-1/2 transform -translate-x-1/2 text-center flex flex-row text-gray-600 items-center text-md md:text-xl transition-opacity duration-500 ease-in-out',
          showArrow ? 'opacity-100' : 'opacity-0 pointer-events-none'
        ]"
        @click="scrollToAbout"
    >
      <span class="m-1 md:m-2">{{ t('scrollText') }}</span>
      <svg class="w-[16px] md:w-[20px] h-[8px] md:h-[10px]" viewBox="0 0 150 82" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path class="stroke-gray-600" d="M145.711 3.93398L75 74.6447L4.28932 3.93398" stroke-width="15"/>
      </svg>
    </div>
  </section>
</template>