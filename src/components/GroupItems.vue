<template>
  <v-container>
    <v-row>
      <v-col>
        <v-sheet class="mx-auto" max-width="1500">
          <h3 align="center" class="mb-4">{{ title }}</h3>
          <v-divider light></v-divider>
          <v-slide-group v-model="model" class="pa-4" center-active show-arrows>
            <v-slide-item v-for="(card, index) in gamesList" :key="index">
              <router-link :to="`/about/${card.id}`">
                <v-card class="ma-4" height="150" width="150">
                  <v-img
                    :src="card.src"
                    class="white--text align-end"
                    height="100px"
                  >
                  </v-img>
                  <v-card-subtitle v-text="card.title"></v-card-subtitle>
                </v-card>
              </router-link>
            </v-slide-item>
          </v-slide-group>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: ["title", "gamesList"],
  data: () => ({
    model: null,
    cards: [
      {
        id: 1,
        title: "Pre-fab homes",
        src: "https://cdn.vuetifyjs.com/images/cards/house.jpg",
      },
      {
        id: 2,
        title: "Favorite road",
        src: "https://cdn.vuetifyjs.com/images/cards/road.jpg",
      },
      {
        id: 3,
        title: "Best airlines",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 4,
        title: "Best airlines1",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 5,
        title: "Best airlines2",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 6,
        title: "Best airlines3",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },
      ,
      {
        id: 7,
        title: "Best airlines4",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 8,
        title: "Best airlines5",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 9,
        title: "Best airlines6",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 10,
        title: "Best airlines7",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },

      {
        id: 11,
        title: "Best airlines8",
        src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
      },
    ],
  }),
};
</script>
