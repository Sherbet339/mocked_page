<template>
  <v-container>
    <v-menu offset-y min-width="0">
      <template v-slot:activator="{ on, attrs }">
        <div class="list-btn">
          <v-btn text v-bind="attrs" v-on="on"
            >{{ title }} <v-icon>mdi-chevron-down</v-icon></v-btn
          >
        </div>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
          @click="&quot;&quot;;"
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-container>
</template>
  
<script>
export default {
  props: ["title", "items"],
  data() {
    return {};
  },
};
</script>