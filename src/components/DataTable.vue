<template>
  <v-container>
    <v-row>
      <v-card>
        <v-card-title>
          Random beers
        </v-card-title>
        <v-card-subtitle>
          <p>Uh oh. There is nothing there. Using the data at <a
              href="https://random-data-api.com/">https://random-data-api.com/</a>, populate the table
            below with headers and make it searchable. Also, expand the table to full width of the container. Let Bob
            know when complete.</p>
        </v-card-subtitle>
        <v-data-table :headers="headers" :items="showedBeers" :items-per-page="10" width="100">
          <template #top>
            <v-text-field v-model="searchString" label="Search" />
          </template>
        </v-data-table>
      </v-card>
    </v-row>
    <v-row>

    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    headers: [
      { text: 'Name', value: 'name' },
      { text: 'Alcohol', value: 'alcohol' },
      { text: 'Style', value: 'style' },
      { text: 'Brand', value: 'brand' },
    ],
    beers: [],
    searchString: '',
  }),
  computed: {
    showedBeers() {
      if (this.searchString.length == 0) {
        return this.beers;
      } else {
        return this.beers.filter((beer) => beer.name.includes(this.searchString) ||
          beer.alcohol.includes(this.searchString) ||
          beer.style.includes(this.searchString) ||
          beer.brand.includes(this.searchString))

      }
    }
  },
  methods: {
    getRandomData() {
      axios.get("https://random-data-api.com/api/v2/beers?size=50").then((response) => {
        this.beers = response.data;
      })
    },
  },
  mounted() {
    this.getRandomData();
  }
};
</script>
