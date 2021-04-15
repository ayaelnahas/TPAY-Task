<template>
  <v-container fluid>
    <v-row>
      <v-col>
        <v-app-bar color="black" dark>
          <div class="d-flex align-center">
            <v-img
              alt="Logo"
              class="shrink mr-2"
              contain
              src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
              transition="scale-transition"
              width="45"
            />
            <v-toolbar-title>Application Title</v-toolbar-title>
          </div>
          <v-spacer></v-spacer>
          <div class="d-inline-flex ">
            <v-text-field
              class="mr-2 mt-7"
              label="search"
              append-icon="mdi-magnify"
              single-line
              filled
              clearable
            ></v-text-field>
          </div>

          <v-menu left bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-btn icon v-bind="attrs" v-on="on">
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
            </template>
            <v-list>
              <v-list-item v-for="n in 5" :key="n" @click="() => {}">
                <v-list-item-title>Option {{ n }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-app-bar>
      </v-col>
    </v-row>
  </v-container>
</template>
