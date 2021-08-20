/* eslint-disable @typescript-eslint/explicit-module-boundary-types */
<template>
  <h1>hi</h1>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import axios from "axios";
@Component
export default class PlayerIndex extends Vue {
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  public async created() {
    try {
      await axios
        .get(
          "https://web-sandbox.onefootball.com/assignments/player/data/fabio.json"
        )
        .then((res) => {
          console.log(res.data);
        });
    } catch (error) {
      console.error(error);
    }
  }
}
</script>

<style></style>
