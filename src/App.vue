<template>
  <div id="app">
    <div class="card">
      <div class="center">
        <p>Cycles {{ cycle }}</p>
        <h1>Hello Pomodoro</h1>
        <p>Status: {{ status }}</p>
      </div>
      <!-- get a minute & a second from timer -->
      <h1>{{ Math.floor(timer / 60) }}:{{ Math.floor(timer % 60) }}</h1>

      <div class="center">
        <button v-on:click="start()">Start timer</button>
        <button v-on:click="pause()">Pause timer</button>
        <button v-on:click="reset()">Reset cycles</button>
      </div>
    </div>
  </div>
</template>

<script>
let counter;
export default {
  name: "App",
  data() {
    return {
      timer: 3,
      cycle: 0,
      status: "study",
    };
  },
  methods: {
    start() {
      this.stop();
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
html {
  overflow: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  width: 100vw;
  position: fixed;
  top: 0;
  left: 0;
  /* center the card */
  display: flex;
  align-items: center;
  justify-content: center;
  color: #31000baf;
  background-image: url("../src/assets/bg-fruit.jpg");
}
.card {
  width: 50%;
  height: 50%;
  background: rgba(250, 219, 228, 0.8);
  box-shadow: 1px 2px 3px rgba(49, 0, 11, 0.5);
  border-radius: 20px;
  padding: 20px;
  /* styling items inside card */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.center {
  text-align: center;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
button {
  padding: 10px;
  border: none;
  background-color: rgba(255, 121, 161, 0.5);
  box-shadow: 1px 2px 3px rgba(49, 0, 11, 0.5);
  border-radius: 10px;
  color: #31000baf;
}
button:hover {
  box-shadow: inset 1px 2px 3px rgba(49, 0, 11, 0.5);
}
@media screen and (max-width: 1000px) {
  .card {
    width: 70%;
  }
}
@media screen and (max-width: 600px) {
  .card {
    width: 100%;
  }
}
</style>
