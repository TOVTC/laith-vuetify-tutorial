<template>
    <v-navigation-drawer
        expand-on-hover
        rail
    >
    <v-list>
        <v-list-item
        prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
        title="Sandra Adams"
        subtitle="sandra_a88@gmailcom"
        ></v-list-item>
    </v-list>
    <v-divider />

    <v-list density="compact" nav>
        <!-- you can find a list of icons in the documentation -->
        <v-list-item
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        />
        <v-list-item
        prepend-icon="mdi-dialpad"
        title="Grayspace Gallery"
        value="color"
        />
    </v-list>

    </v-navigation-drawer>
</template>