<template>
  <v-app>
    <v-app-bar color="white" app>
      <div class="d-flex align-center">
        <h3>Saba</h3>
        <v-icon small color="#7f5df7">mdi-circle</v-icon>

        
      </div>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main> </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data() {
    return {
      items: [
        { title: "Breakfast & brunch" },
        { title: "New American" },
        { title: "Sushi" },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/_global.scss";
</style>
