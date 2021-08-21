<template>
  <v-app>
    <v-main>
      <!-- <router-view /> -->
      <PlayerIndex />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import PlayerIndex from "./components/PlayerIndex.vue";
@Component({
  components: {
    PlayerIndex,
  },
})
export default class App extends Vue {}
</script>
