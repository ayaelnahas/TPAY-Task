<template>
  <div>
    <v-container>
      <v-row>
        <Category @selectedGames="showSelectedGames"></Category>
      </v-row>
      <v-row>
        <Featured-card
          title="Featured Game"
          :game="featuredGame"
        ></Featured-card>
      </v-row>
      <v-row>
        <GroupItems
          title="Most Recommended"
          :gamesList="recommendedGames"
        ></GroupItems>
      </v-row>
      <v-row>
        <GroupItems title="Most Popular" :gamesList="popularGames"></GroupItems>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

import Category from "../components/GroupChips";
import GroupItems from "../components/GroupItems";
import FeaturedCard from "../components/FeaturedCard.vue";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Category,
    GroupItems,
    FeaturedCard,
  },
  data: () => ({
    allGames: [],
    recommendedGames: [],
    popularGames: [],
    featuredGame: {},
  }),
  mounted() {
    this.getGameList();
  },
  methods: {
    showSelectedGames(value) {

      this.recommendedGames = this.allGames.filter((element) =>
        value.some((el) => element.id === el && element.type == "recommended")
      );

      this.popularGames = this.allGames.filter((element) =>
        value.some((el) => element.id === el && element.type == "popular")
      );
    },
    getGameList() {
      axios
        .get(`https://my-json-server.typicode.com/ayaelnahas/mockjson/games`)
        .then((response) => {
          this.allGames = response.data;
          this.featuredGame = response.data[0];
          this.recommendedGames = response.data.filter(
            (el) => el.type == "recommended"
          );
          this.popularGames = response.data.filter(
            (el) => el.type == "popular"
          );
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
