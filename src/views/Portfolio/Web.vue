<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>Web</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="project.dialog"
        lazy
        max-width="1000"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="project.poster"
                :alt="project.title"
                height="230"
                lazy-src="./img/fluid-loader.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="project.dialog">
          <v-img :src="project.poster"></v-img>
          <v-card-text>
            <h3 class="headline mb-0">
              <span>WEB</span>
            </h3>
            <v-chip color="green" text-color="white">{{project.tech.tech1}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech2}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech3}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech4}}</v-chip>
          </v-card-text>
          <v-card-actions>
            <v-btn flat large dark color="green" :href="project.git" target="_blank">
              <v-icon left>fab fa-github</v-icon>GitHub
            </v-btn>
            <v-btn large flat dark color="green" :href="project.demo" target="_blank">
              <v-icon left>fas fa-desktop</v-icon>Demo
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: "Web Portfolio",
    titleTemplate: "%s ← Katou's Place",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Quentin BUXO's Web Portfolio Vue Vue.js Nuxt Nuxt.js HTML CSS Vuetify Axios GraphQL JavaScript Web Developer Front-End Frontend Designer App Responsive"
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
          "Quentin BUXO's Web Portfolio Vue Vue.js Nuxt Nuxt.js HTML CSS Vuetify Axios GraphQL JavaScript Web Developer Front-End Frontend Designer App Responsive"
      }
    ]
  },
  data() {
    return {
      dialog: false,
      projects: [
         {
          dialog: false,
          title: "Groupomania",
          git: "https://github.com/KatouProg/QuentinBuxo_7_18122021_test",
          demo: "https://youtu.be/oT3Uz9oo9W8",
          tech: {
            tech1: "VueJs",
            tech2: "JavaScript",
            tech3: "NodeJs",
            tech4: "MySql"
          },
          poster: "https://zupimages.net/up/22/16/p7zm.png"
        },

        {
          dialog: false,
          title: "OHMYFOOD!",
          git: "https://github.com/KatouProg/QuentinBuxo_3_19082021",
          demo: "https://katouprog.github.io/QuentinBuxo_3_19082021/",
          tech: {
            tech1: "Html",
            tech2: "Css",
            tech3: "Scss",
            tech4: "Animations"
          },
          poster: "https://zupimages.net/up/22/21/o83a.png"
        }
      ]
    };
  }
};
</script>

<style  scoped>
</style>