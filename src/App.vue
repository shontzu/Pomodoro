<template>
  <div id="app">
    <Card />
    <MusicPlayer />
    <Attribution />
  </div>
</template>

<script>
import Card from "../src/components/Card.vue";
import MusicPlayer from "../src/components/MusicPlayer.vue"
import Attribution from "../src/components/Attribution.vue"

export default {
  name: "App",
  components: {
    Card,
    MusicPlayer,
    Attribution,
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
  display: flex;
  flex-direction: column;
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
