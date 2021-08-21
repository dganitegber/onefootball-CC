<template>
  <player-index />
</template>

<script lang="ts">
import Vue from "vue";
import PlayerIndex from "../components/PlayerIndex.vue";

export default Vue.extend({
  name: "Home",

  components: {
    PlayerIndex,
  },
});
</script>
