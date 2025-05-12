<script setup>
import {useI18n} from "vue-i18n";
const { t } = useI18n()
</script>

<template>
  <section id="about" class="p-8 bg-gray-100">
    <h2 class="text-3xl font-semibold mb-6 text-center md:text-left">{{ t('about.title') }}</h2>
    <div class="flex flex-col md:flex-row items-center gap-12 md:gap-16">
      <!-- Text and download buttons -->
      <div class="flex flex-col items-center md:items-start">
        <p class="text-lg text-gray-700 mb-6 max-w-2xl text-center md:text-left">{{ t('about.intro') }}</p>
        <p class="text-lg text-gray-700 mb-6 max-w-2xl text-center md:text-left">{{ t('about.more') }}</p>
        <div class="flex flex-wrap gap-6 justify-center md:justify-start">
          <a href="/resume/nl_compact.pdf" download class="bg-gray-700 text-white py-3 px-6 rounded-lg hover:bg-gray-800 focus:ring-2 focus:ring-gray-500 transition transform hover:scale-105">CV Compact</a>
          <a href="/resume/nl_detailed.pdf" download class="bg-gray-700 text-white py-3 px-6 rounded-lg hover:bg-gray-800 focus:ring-2 focus:ring-gray-500 transition transform hover:scale-105">CV Gedetailleerd</a>
<!--          <a href="/resume/en_compact.pdf" download class="bg-gray-700 text-white py-3 px-6 rounded-lg hover:bg-gray-800 focus:ring-2 focus:ring-gray-500 transition transform hover:scale-105">CV EN Compact</a>-->
<!--          <a href="/resume/en_detailed.pdf" download class="bg-gray-700 text-white py-3 px-6 rounded-lg hover:bg-gray-800 focus:ring-2 focus:ring-gray-500 transition transform hover:scale-105">CV EN Detailed</a>-->
        </div>
      </div>
    </div>
  </section>
</template>