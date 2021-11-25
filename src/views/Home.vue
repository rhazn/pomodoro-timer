<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Timer :startSeconds="25 * 60" @timePassed="onTimePassed()" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Timer from "../components/Timer.vue";

export default defineComponent({
  components: {
    Timer,
  },
  methods: {
    onTimePassed() {
      console.log("time passed!");
    },
  },
});
</script>
