<template>
  <v-container>
    <v-row>
      <v-col>
        <h3 align="center" class="mb-4">{{ title }}</h3>
        <v-divider light ></v-divider>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-card class="mx-auto" max-width="500">
          <v-img
            :src="game.src"
            height="200px"
          ></v-img>

          <v-card-title>
            {{game.title}}
          </v-card-title>

          <v-card-subtitle>
            {{game.type}}
          </v-card-subtitle>

          <v-card-text>
            <div>
              {{game.body}}
            </div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: ["title","game"],
  data: () => ({
    show: false,
  }),
};
</script>
