<template>
  <div id="app">
    <section class="playlist">
      <Playlist />
    </section>
  </div>
</template>

<script>
import Playlist from "./components/Playlist.vue";

export default {
  name: "App",
  components: {
    Playlist,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}

#app {
  font-family: "Quicksand", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 40px;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  font-family: sans-serif;

  background: linear-gradient(270deg, #243766, #bd13c6, #73f9ee);
  background-size: 600% 600%;

  -webkit-animation: AnimationName 30s ease infinite;
  -moz-animation: AnimationName 30s ease infinite;
  animation: AnimationName 30s ease infinite;
}

@-webkit-keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
@-moz-keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
@keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.playlist {
  margin-top: 5px;
  position: relative;
  text-align: center;
  width: 380px;
  border-radius: 15px;
  overflow: hidden;
  background: gainsboro;
  box-shadow: 0px 6px 15px (#ffcbdd);
}

i {
  cursor: pointer;
}
</style>
