<template>
  <div>
    <DetailedCard title="Game Details"></DetailedCard>
    <GroupItems
      title="Recommended List"
      :gamesList="recommendedGames"
    ></GroupItems>
  </div>
</template>

<script>
import DetailedCard from "@/components/DetailedCard";
import GroupItems from "@/components/GroupItems";
import axios from "axios";

export default {
  name: "Home",
  components: {
    DetailedCard,
    GroupItems,
  },
  data: () => ({
    recommendedGames: [],
  }),
  mounted() {
    axios
      .get(`https://my-json-server.typicode.com/ayaelnahas/mockjson/games`)
      .then((response) => {
        this.recommendedGames = response.data.filter(
          (el) => el.type == "recommended"
        );
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>
