<template>
  <div id="app">
    <h1>Hello</h1>
    <!--     <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->

    <input
      @input="updateVideo()"
      type="range"
      min="0"
      max="17"
      v-model="position"
    />

    <h1>{{ this.position }}</h1>

    <vue-plyr ref="video1">
      <video poster="poster.png" src="video.mp4" preload="auto">
        <source src="./assets/Timelapse.mp4" type="video/mp4" size="720" />
      </video>
    </vue-plyr>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    // HelloWorld
  },
  data: function() {
    return {
      position: 0
    };
  },
  methods: {
    updateVideo() {
      this.$refs.video1.player.currentTime = Number(this.position);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
