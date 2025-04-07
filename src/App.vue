<script setup>
import HeroSection from "./sections/HeroSection.vue";
import { onMounted } from "vue";

import { useI18n } from "vue-i18n";
const { t } = useI18n()

onMounted(() => {
  alert(t('wip_message'))
})
</script>

<template>
  <div>
    <HeroSection />
  </div>
</template>