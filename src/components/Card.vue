<template>
  <div class="card">
    <div class="center">
      <p>Cycles {{ cycle }}</p>
      <h1>Hello Pomodoro</h1>
      <p>Status: {{ status }}</p>
    </div>
    <!-- get a minute & a second from timer -->
    <h1>{{ Math.floor(timer / 60) }}:{{ Math.floor(timer % 60) }}</h1>

    <div class="center">
      <button @click.prevent="start()">Start timer</button>
      <button @click.prevent="pause()">Pause timer</button>
      <button @click.prevent="reset()">Reset pomodoro</button>
    </div>
  </div>
</template>

<script>
let counter;
export default {
  name: "Card",
  data() {
    return {
      timer: 3,
      cycle: 0,
      status: "study",
    };
  },
  methods: {
    start() {
      this.pause();
      counter = setInterval(() => {
        if (this.timer === 0) {
          this.pause();
          this.cycle++;
          this.toggle();
          this.restart();
          this.start();
        } else {
          this.timer--;
        }
      }, 1000);
    },
    pause() {
      clearInterval(counter);
    },
    reset() {
      this.restart();
      this.cycle = 0;
      this.status = "study";
    },
    restart() {
      clearInterval(counter);
      this.timer = 3;
    },
    toggle() {
      // if cycle=even, status=study
      if (this.cycle % 2 === 0) {
        this.status = "study";
      } else {
        this.status = "break";
      }
    },
  },
};
</script>

<style>
</style>