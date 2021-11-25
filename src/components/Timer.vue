<template>
  <div class="timer">
    <div class="timer__minutes">
      {{ String(Math.floor(seconds / 60)).padStart(2, "0") }}
    </div>
    <div class="timer__colon">:</div>
    <div class="timer__seconds">
      {{ String(seconds % 60).padStart(2, "0") }}
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    startSeconds: Number,
  },
  data() {
    return {
      seconds: this.startSeconds || 1500,
    };
  },
  mounted(): void {
    setInterval(() => {
      this.seconds -= 1;
    }, 1000);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.timer {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
</style>
