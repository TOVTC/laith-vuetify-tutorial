<template>
    <v-row>
        <!-- the grid system in Vuetify works the same as the grid system in Bootstrap -->
        <!-- use the v-for directive to make multiple columns using a loop -->
        <v-col
        v-for="n in 200"
        cols="1"
        :key=n
        >
            <v-card>
                <!-- picsum is a random image generator -->
                <!-- aspect-ratio turns the images to squares -->
                <!-- cover sets the way the image takes up space in the square -->
                <v-img
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                aspect-ratio="1"
                cover
                />
            </v-card>
        </v-col>
    </v-row>
</template>