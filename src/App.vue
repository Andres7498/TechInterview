<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img alt="Vuetify Logo" class="shrink mr-2" contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png" transition="scale-transition" width="40" />

        <v-img alt="Vuetify Name" class="shrink mt-1 hidden-sm-and-down" contain min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png" width="100" />
      </div>
      <v-spacer></v-spacer>
      <v-btn to="/" color="white" plain rounded>
        Home
      </v-btn>
      <v-btn to="/about" color="white" plain rounded>
        About
      </v-btn>
      <v-btn to="/data" color="white" plain rounded>
        Data
      </v-btn>

    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
    <v-footer color="primary lighten-1" padless>
      <v-card flat tile class="primary lighten-1 text-center" id="App" style="max-width: 800px;">
        <v-card-text class="white--text">
          <ul>
            <!-- Render ecosystem links -->
            <li v-for="(item, index) in ecosystem" :key="index">
              <a :href="item.href" class="white--text">{{ item.text }}</a>
            </li>
          </ul>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-text class="white--text">
          <ul>
            <!-- Render important links -->
            <li v-for="(item, index) in importantLinks" :key="index">
              <a :href="item.href" class="white--text">{{ item.text }}</a>
            </li>
          </ul>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-text class="white--text">
          <ul>
            <!-- Render 'what's next' links -->
            <li v-for="(item, index) in whatsNext" :key="index">
              <a :href="item.href" class="white--text">{{ item.text }}</a>
            </li>
          </ul>
        </v-card-text>
      </v-card>
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
