<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <!-- App Bar content -->
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <v-footer color="primary lighten-1" padless>
      <v-row justify="center">
        <v-col cols="12" sm="8" md="6" lg="4">
          <v-card flat tile class="primary lighten-1 text-center" id="App" style="max-width: 100%;">
            <v-card-text class="white--text">
              <ul class="footer-list">
                <!-- Render ecosystem links -->
                <li v-for="(item, index) in ecosystem" :key="index">
                  <a :href="item.href" class="white--text">{{ item.text }}</a>
                </li>
              </ul>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" sm="8" md="6" lg="4">
          <v-card flat tile class="primary lighten-1 text-center" id="App" style="max-width: 100%;">
            <v-card-text class="white--text">
              <ul class="footer-list">
                <!-- Render important links -->
                <li v-for="(item, index) in importantLinks" :key="index">
                  <a :href="item.href" class="white--text">{{ item.text }}</a>
                </li>
              </ul>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" sm="8" md="6" lg="4">
          <v-card flat tile class="primary lighten-1 text-center" id="App" style="max-width: 100%;">
            <v-card-text class="white--text">
              <ul class="footer-list">
                <!-- Render 'what's next' links -->
                <li v-for="(item, index) in whatsNext" :key="index">
                  <a :href="item.href" class="white--text">{{ item.text }}</a>
                </li>
              </ul>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    ecosystem: [
      {
        text: "vuetify-loader",
        href: "https://github.com/vuetifyjs/vuetify-loader",
      },
      {
        text: "github",
        href: "https://github.com/vuetifyjs/vuetify",
      },
      {
        text: "awesome-vuetify",
        href: "https://github.com/vuetifyjs/awesome-vuetify",
      },
    ],
    importantLinks: [
      {
        text: "Documentation",
        href: "https://vuetifyjs.com",
      },
      {
        text: "Chat",
        href: "https://community.vuetifyjs.com",
      },
      {
        text: "Made with Vuetify",
        href: "https://madewithvuejs.com/vuetify",
      },
      {
        text: "Twitter",
        href: "https://twitter.com/vuetifyjs",
      },
      {
        text: "Articles",
        href: "https://medium.com/vuetify",
      },
    ],
    whatsNext: [
      {
        text: "Explore components",
        href: "https://vuetifyjs.com/components/api-explorer",
      },
      {
        text: "Select a layout",
        href: "https://vuetifyjs.com/getting-started/pre-made-layouts",
      },
      {
        text: "Frequently Asked Questions",
        href: "https://vuetifyjs.com/getting-started/frequently-asked-questions",
      },
    ],
  }),
};
</script>

<style scoped>
.footer-list {
  list-style-type: none; /* Remove bullets */
  padding-left: 0; /* Remove left padding */
}
</style>
