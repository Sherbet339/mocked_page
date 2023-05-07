<template>
  <v-app>
    <v-app-bar color="white" app>
      <div class="d-flex align-center">
        <h3 style="color: #7f5df7;">Saba</h3>
        <v-icon class="pl-1" small color="#c5b7fa">mdi-circle</v-icon>
      </div>
      <v-spacer></v-spacer>
      <MenuDropdown :title="'New arrival'" :items="items"></MenuDropdown>
      <MenuDropdown :title="'Women'" :items="items"></MenuDropdown>
      <MenuDropdown :title="'Men'" :items="items"></MenuDropdown>
      <MenuDropdown :title="'Outlet'" :items="items"></MenuDropdown>
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-cart</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main> </v-main>
  </v-app>
</template>

<script>
import MenuDropdown from "./components/MenuDropdown.vue";

export default {
  name: "App",
  components: { MenuDropdown },
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
