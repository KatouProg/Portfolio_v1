<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>E-shop</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="video.dialog"
        lazy
        max-width="800"
        v-for="video in videos"
        :key="video.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="video.poster"
                aspect-ratio="1.7778"
                :alt="video.title"
                lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
                contain
              ></v-img>
              <v-card-title primary-title class="justify-center">{{video.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="video.dialog">
          <plyr>
            <div class="plyr__video-embed">
              <iframe :src="video.href" allowfullscreen allowtransparency allow="autoplay"></iframe>
            </div>
          </plyr>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
import { PlyrVideo } from "vue-plyr";

export default {
  metaInfo: {
    title: "E-shop",
    titleTemplate: "%s ← Katou's Place",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Quentin BUXO's Services Adobe Premire After Effects Video Ad's Social Media Logo Animation Instagram Facebook Video Editing Advetising"
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Katou's Place" },
      { property: "og:site_name", content: "Katou's Place" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://katou.place" },
      {
        property: "og:image",
        content: "./img/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content:
          "Quentin BUXO's Services Adobe Premire After Effects Video Ad's Social Media Logo Animation Instagram Facebook Video Editing Advetising"
      }
    ]
  },
  components: { plyr: PlyrVideo },
  data() {
    return {
      dialog: false,
      videos: [
        {
          dialog: false,
          title: "Pika-Pika",
          href: "http://pika-pika.fr/",
          type: "text/html",
          youtube: "XP8j7NA_wzc",
          poster: "https://zupimages.net/up/22/16/flhk.png"
        }
      ]
    };
  }
};
</script>

<style  scoped>
@import "../../../node_modules/vue-plyr/dist/vue-plyr.css";
</style>