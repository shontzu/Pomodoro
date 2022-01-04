<template>
  <audio controls autoplay muted>
    <source
      src="../assets/Makaih Beats by Free Music Archive (FMA) on makaih.com is licensed under Creative Commons Liscense.mp3"
    />
  </audio>
</template>

<script>
export default {};
</script>

<style>
audio {
  width: 50%;
  height: 20px;
  margin-top:20px;
}
@media screen and (max-width: 1000px) {
  audio {
    width: 70%;
  }
}
@media screen and (max-width: 600px) {
  audio {
    width: 100%;
  }
}
</style>