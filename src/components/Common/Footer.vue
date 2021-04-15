<template>
  <v-card height="150">
    <v-footer
      absolute
      color="grey lighten-1"
      class="font-weight-medium"
    >
      <v-col
        class="text-center"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Application Title</strong>
      </v-col>
    </v-footer>
  </v-card>
</template>