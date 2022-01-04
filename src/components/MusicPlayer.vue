<template>
  <div>
    <audio controls autoplay loop>
      <source
        src="../assets/Makaih Beats by Free Music Archive (FMA) on makaih.com is licensed under Creative Commons Liscense.mp3"
      />
    </audio>
  </div>
</template>

<script>

export default {
    name: 'MusicPlayer',
};
</script>

<style>
audio {
  margin-top:20px;
  margin-bottom:20px;
}
audio::-webkit-media-controls-play-button,
     audio::-webkit-media-controls-panel {
     background-color: pink;
     color: #31000baf;
     }
</style>