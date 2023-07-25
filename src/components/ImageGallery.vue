<script setup>
import { defineProps } from "vue";

const p = defineProps(["isWithColour"]);

const copyUrl = async (url) => {
    // copies the url of the image to clipboard
    await navigator.clipboard.writeText(url);
}
</script>

<template>
    <!-- wrap the row in a card to add styling -->
    <!-- Vuetify has its own CSS classes -->
    <v-card class="mx-5 my-2 pa-3">
        <v-row>
            <!-- the grid system in Vuetify works the same as the grid system in Bootstrap -->
            <!-- use the v-for directive to make multiple columns using a loop -->
            <v-col
            v-for="n in 200"
            cols="4"
            sm="3"
            md="2"
            lg="1"
            :key=n
            >
            
            <!-- wrap with hover and use v-slot to enable animations -->
            <v-hover
            v-slot="{isHovering, props}">
                <v-card
                :elevation="isHovering ? 12 : 2"
                v-bind="props"
                @click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColour ? '' : '&grayscale'}`)"
                >
                    <!-- picsum is a random image generator -->
                    <!-- aspect-ratio turns the images to squares -->
                    <!-- cover sets the way the image takes up space in the square -->
                    <!-- the lazy src loads a lower-quality version of the image immediately while the main image loads -->
                    <v-img
                    :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColour ? '' : '&grayscale'}`"
                    :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColour ? '' : '&grayscale'}`"
                    aspect-ratio="1"
                    cover
                    >
                    <!-- use a slot to enable a loading animation on each card -->
                    <template v-slot:placeholder>
                        <v-row
                        class="fill-height ma-0"
                        align="center"
                        justify="center"
                        >
                        <v-progress-circular
                        indeterminate
                        color="grey-lighten-5"
                        ></v-progress-circular>
                    </v-row>
                    </template>
                    </v-img>
                </v-card>
            </v-hover>
            </v-col>
        </v-row>
    </v-card>
</template>