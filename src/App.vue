<script setup>
import ImageGallery from "./components/ImageGallery.vue";
import SideBar from "./components/SideBar.vue"
</script>

<template>
<v-app>
  <SideBar />
  <v-main>
    <ImageGallery />
  </v-main>
</v-app>
</template>