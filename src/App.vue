<template>
  <v-app>
    <v-main>
      <Header></Header>
      <router-view></router-view>
      <Footer></Footer>
    </v-main>
  </v-app>
</template>

<script>
import Header from "./components/Common/Header.vue";
import Footer from "./components/Common/Footer.vue";
export default {
  name: "App",
  components: {
    Header,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
