<script setup>
import heroCoverImage from "../assets/hero_cover.jpg"
import heroProfileImage from "../assets/hero_profile.jpg"

import { ref, onMounted } from 'vue'

import {useI18n} from "vue-i18n";
const { t } = useI18n()

const isMobile = ref(false)
const isResumeDropdownOpen = ref(false)

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
          <div class="h-fit bg-teal-600 shadow-lg shadow-cyan-500/50 rounded-md overflow-hidden">
            <button @click="isResumeDropdownOpen = !isResumeDropdownOpen" class="bg-cyan-500 w-full rounded-b-sm px-3 py-2 text-sm font-semibold text-white focus:outline-none">Download {{ t('cv')}}</button>
            <ul v-if="isResumeDropdownOpen" class="flex flex-col text-xs font-semibold text-white space-y-2 px-4 py-2">
              <li><a href="/resume/nl_detailed.pdf" target="_blank" rel="noopener noreferrer" class="focus:outline-none">{{ t('detailed_nl') }}</a></li>
              <li><a href="/resume/nl_compact.pdf" target="_blank" rel="noopener noreferrer" class="focus:outline-none">{{ t('compact_nl') }}</a></li>
              <li><a href="/resume/en_detailed.pdf" target="_blank" rel="noopener noreferrer" class="hidden focus:outline-none">{{ t('detailed_en') }}</a></li>
              <li><a href="/resume/en_compact.pdf" target="_blank" rel="noopener noreferrer" class="hidden focus:outline-none">{{ t('compact_en') }}</a></li>
            </ul>
          </div>
          <a href="#contact" class="hidden rounded-md bg-green-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-green-500/50 focus:outline-none h-fit">{{ t('contact_button')}}</a>
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
      <div class="grow h-fit bg-teal-600 shadow-lg shadow-cyan-500/50 rounded-md overflow-hidden">
        <button @click="isResumeDropdownOpen = !isResumeDropdownOpen" class="bg-cyan-500 w-full rounded-b-sm px-3 py-2 text-sm font-semibold text-white focus:outline-none">Download {{ t('cv')}}</button>
        <ul v-if="isResumeDropdownOpen" class="flex flex-col text-xs font-semibold text-white space-y-2 px-4 py-2">
          <li><a href="/resume/nl_detailed.pdf" target="_blank" rel="noopener noreferrer" class="focus:outline-none">{{ t('detailed_nl') }}</a></li>
          <li><a href="/resume/nl_compact.pdf" target="_blank" rel="noopener noreferrer" class="focus:outline-none">{{ t('compact_nl') }}</a></li>
          <li><a href="/resume/en_detailed.pdf" target="_blank" rel="noopener noreferrer" class="hidden focus:outline-none">{{ t('detailed_en') }}</a></li>
          <li><a href="/resume/en_compact.pdf" target="_blank" rel="noopener noreferrer" class="hidden focus:outline-none">{{ t('compact_en') }}</a></li>
        </ul>
      </div>
      <a href="#contact" class="hidden grow rounded-md bg-green-500 px-3 py-2 text-sm font-semibold text-white shadow-lg shadow-green-500/50 focus:outline-none">{{ t('contact_button')}}</a>
    </div>
  </div>
</template>