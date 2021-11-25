<template>
  <div class="timer" @click="onClicked">
    <div class="timer__numbers">
      {{ String(Math.floor(seconds / 60)).padStart(2, "0") }}
    </div>
    <div class="timer__colon">:</div>
    <div class="timer__numbers">
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
  emits: {
    timePassed: null,
  },
  methods: {
    onClicked() {
      if (this.intervalId !== undefined) {
        this.stopTimer();
      } else {
        this.startTimer();
      }
    },
    startTimer(): void {
      if (this.seconds < 1) {
        return;
      }

      this.intervalId = setInterval(() => {
        this.seconds -= 1;

        if (this.seconds === 0) {
          this.stopTimer();
          this.$emit("timePassed");
        }
      }, 1000);
    },
    stopTimer(): void {
      if (this.intervalId === undefined) {
        return;
      }

      clearInterval(this.intervalId);
      this.intervalId = undefined;
    },
  },
  data() {
    return {
      seconds: this.startSeconds || 1500,
      intervalId: undefined as number | undefined,
    };
  },
  mounted(): void {
    this.startTimer();
  },
});
</script>

<style scoped>
.timer {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;

  cursor: pointer;
}

.timer__numbers {
  font-size: 7rem;
  color: var(--highlight-color);
}

.timer__colon {
  font-size: 5rem;
  color: var(--text-color);
}
</style>
