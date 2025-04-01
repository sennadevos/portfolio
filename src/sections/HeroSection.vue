<script setup>
import heroCoverImage from "../assets/hero_cover.jpg"
import heroProfileImage from "../assets/hero_profile.jpg"

import { ref, onMounted } from 'vue'

import {useI18n} from "vue-i18n";
const { t } = useI18n()

const isMobile = ref(false)

onMounted(() => {
  const checkMobile = () => {
    isMobile.value = window.innerWidth < 768
  }

  checkMobile()
  window.addEventListener('resize', checkMobile)
})
</script>

<template>
  <div class="relative w-full">
    <!-- Background Image -->
    <img :src="heroCoverImage" alt="Cover Image" class="w-full h-full object-cover"/>

    <!-- Shadow Gradient -->
    <div class="absolute inset-0 bg-gradient-to-t from-black to-transparent"></div>

    <!-- Content Overlay (Desktop) -->
    <div class="hidden md:flex absolute inset-0 flex items-center justify-start px-8 sm:px-12 md:px-16">
      <div class="flex flex-col space-y-5">
        <div class="text-gray-200 max-w-md bg-black/50 p-4 rounded-lg backdrop-blur-sm">
          <h1 class="text-4xl sm:text-5xl font-bold">Senna de Vos</h1>
          <h2>{{ t('subtitle') }}</h2>
          <p class="mt-4 text-lg sm:text-xl">{{ t('bio') }}</p>
        </div>
        <div class="px-4 flex gap-5">
          <a href="#" class="rounded-md bg-cyan-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-cyan-500/50 focus:outline-none">Download {{ t('cv')}}</a>
          <a href="#contact" class="rounded-md bg-green-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-green-500/50 focus:outline-none">{{ t('contact_button')}}</a>
        </div>
      </div>
    </div>
  </div>

  <!-- Content (Mobile) -->
  <div class="md:hidden flex flex-col space-y-5 p-4">
    <div class="text-gray-200 max-w-md">
      <h1 class="text-4xl sm:text-5xl font-bold">Senna de Vos</h1>
      <h2>{{ t('subtitle') }}</h2>
      <p class="mt-4 text-lg sm:text-xl">{{ t('bio') }}</p>
    </div>
    <div class="px-4 flex flex-wrap gap-5">
      <a href="#" class="grow rounded-md bg-cyan-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-cyan-500/50 focus:outline-none">Download {{ t('cv')}}</a>
      <a href="#contact" class="grow rounded-md bg-green-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-green-500/50 focus:outline-none">{{ t('contact_button')}}</a>
    </div>
  </div>
</template>