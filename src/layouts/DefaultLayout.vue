<template>
  <v-app-bar color="teal-darken-4" image="https://picsum.photos/1920/1080?random">
    <template v-slot:image>
      <v-img gradient="to top right, rgba(19,84,122,.8), rgba(128,208,199,.8)"></v-img>
    </template>

    <v-btn to="/login" icon>
      <v-icon>mdi-login</v-icon>
    </v-btn>

    <v-btn to="/" icon>
      <v-icon>mdi-home</v-icon>
    </v-btn>

    <v-app-bar-title>Title</v-app-bar-title>

    <v-spacer> </v-spacer>

    <v-btn to="/about" icon>
      <!-- <v-icon>mdi-about</v-icon> -->
      <v-icon>mdi-information-outline</v-icon>
    </v-btn>

    <v-btn to="/admin" icon>
      <v-icon>mdi-heart</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>mdi-dots-vertical</v-icon>
    </v-btn>
  </v-app-bar>
</template>
