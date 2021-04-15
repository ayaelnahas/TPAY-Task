<template>
  <v-container>
    <v-row justify="space-around">
      <v-col cols="12" sm="10" md="12" lg="12">
        <v-sheet elevation="0" class="pa-4">
          <v-chip-group
            show-arrows
            v-model="value"
            active-class="v-slide-item--active"
          >
            <v-chip v-for="(tag, index) in tags" :key="index">
              {{ tag.name }}
            </v-chip>
          </v-chip-group>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    tags: [],
    value: null,
  }),
  watch: {
    value: "show",
  },
  mounted() {
    this.getData();
  },
  methods: {
    show() {
      let selectedGames = this.tags.filter((el, index) => index == this.value)[0].gameId;
      this.$emit('selectedGames',selectedGames)
    },
    getData() {
      axios
        .get(
          "https://my-json-server.typicode.com/ayaelnahas/mockjson/categories"
        )
        .then((response) => {
          this.tags = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
