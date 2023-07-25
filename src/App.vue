<script setup>
import ImageGallery from "./components/ImageGallery.vue";
import SideBar from "./components/SideBar.vue";
import { ref } from "vue";

const isWithColour = ref(true);

const onSelectOption = (isColour) => {
  isWithColour.value = isColour;
}
</script>

<template>
<v-app>
  <SideBar @selectOption="onSelectOption"/>
  <v-main>
    <ImageGallery :isWithColour="isWithColour"/>
  </v-main>
</v-app>
</template>