<template>
  <v-container>
    <v-row class="mt-4">
      <v-col>
        <h2 align="center" class="mb-4">{{ title }}</h2>
        <v-card class="mx-auto mb-10" max-width="500">
          <v-img :src="detailedCard.src" height="200px"></v-img>

          <v-card-title> {{ detailedCard.title }} </v-card-title>

          <v-card-subtitle> Category: {{ detailedCard.type }} </v-card-subtitle>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-card-subtitle>See More</v-card-subtitle>
            <v-btn icon @click="show = !show">
              <v-icon>
                {{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon
              >
            </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>
              <v-card-text>
                {{ detailedCard.body }}
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "DetailedCard",
  props: ["title"],
  data: () => ({
    show: false,
    detailedCard: {},
    id: null,
  }),
  watch: {
    $route: function() {
      this.getDetailedCard();
    },
  },
  mounted() {
    this.getDetailedCard();
  },
  methods: {
    getDetailedCard() {
      this.id = this.$route.params.id;
      axios
        .get(
          `https://my-json-server.typicode.com/ayaelnahas/mockjson/games/${this.id}`
        )
        .then((response) => {
          this.detailedCard = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
