<script setup>
import {useI18n} from "vue-i18n";
const { t } = useI18n()

import heroCoverImage from "../assets/hero_cover.jpg"
import heroProfileImage from "../assets/hero_profile.jpg"
</script>

<template>
  <div>
    <img :src="heroCoverImage" alt="Cover Image" />
    <img :src="heroProfileImage" alt="Profile Image" />
    <h1>Senna de Vos</h1>
    <h2>{{ t('subtitle') }}</h2>
    <p>{{ t('bio') }}</p>
  </div>
  <div>
    <a href="#">Download {{ t('cv')}}</a>
    <a href="#contact">{{ t('contact_button')}}</a>
  </div>
</template>