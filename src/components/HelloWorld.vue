<template>
  <v-container>
    <v-row>
      <v-col cols="6">
        <h2>Welcome to the Tech Interview</h2>
        Youre doing great so far. Keep it up.
        <v-img alt="Cat with hat" class="shrink mr-2" contain src="../assets/catmeme.jpg" transition="scale-transition"
          width="100%" />
      </v-col>
      <v-col cols="6">
        <v-row>
          Something seems to be wrong. There should be a nav up there ^^^
        </v-row>
        <v-row>
          Add a nav to the view /data.
        </v-row>
      </v-col>
    </v-row>

    
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    
  }),
};
</script>
