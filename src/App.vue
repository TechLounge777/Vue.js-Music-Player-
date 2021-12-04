<template>
  <div id="app">
    <section class="player">
      <div class="top-nav">
        <div id="top-nav-controls">
          <img
            id="repeat-playlist"
            src="../public/repeat-white.png"
            width="20"
            height="20"
            alt="repeat-icon"
          />
          <i class="fas fa-redo"></i>
          <i class="fas fa-random"></i>
        </div>
        <div id="bars">
          <i class="fas fa-bars"></i>
        </div>
      </div>
      <div class="cover-photo">
        <img
          src="../public/icona-pop-hq.jpg"
          width="380"
          height="360"
          alt="icon-pop-cover-photo"
        />

        <div class="song-info">
          <h1 class="artist">Icona Pop</h1>
          <h2 class="song-title">Still don't know</h2>
        </div>
      </div>

      <div class="progress-container">
        <div class="progress-line">
          <span></span>
          <div class="timer">
            <span class="current"></span>
            <span class="current"></span>
            <span></span>
          </div>
        </div>
      </div>

      <div class="bottom-navButtons">
        <i id="share" class="fas fa-share-alt"></i>
        <div class="bottom-controls">
          <i id="previous" class="fas fa-step-backward"></i>
          <i id="play" class="fas fa-play-circle"></i>
          <i id="next" class="fas fa-step-forward"></i>
        </div>
        <i id="like" class="fas fa-heart"></i>
      </div>
    </section>
    <section class="playlist"></section>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
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
  color: #000;
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

.player {
  position: relative;
  text-align: center;
  width: 380px;
  border-radius: 15px;
  overflow: hidden;
  background: gainsboro;
  box-shadow: 0px 6px 15px (#ffcbdd);
}

.player i {
  cursor: pointer;
}

.top-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: absolute;
  top: 0;
  width: 380px;
  min-height: 15%;
  background: rgb(0, 0, 0);
  background: rgba(0, 0, 0, 0.5); /* Black see-through */
  color: #fff;
}

#top-nav-controls {
  display: flex;
  align-items: center;
  gap: 30px;
  padding-top: 30px;
  padding-left: 130px;
}

#bars {
  display: flex;
  align-items: center;
  padding-top: 30px;
  padding-right: 40px;
  padding-left: 40px;
  color: darkgray;
}

.cover-photo {
  width: 380px;
}

.song-info {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  bottom: 30%;
  left: 35%;
  color: #fff;
}
.artist {
  display: flex;
  font-size: 18px;
}
.song-title {
  display: flex;
  font-size: 16px;
  font-weight: 400;
}

.progress-container {
  width: 100%;
  height: 7px;
  background: white;
  border-radius: 50px;
  cursor: pointer;
}

.progress-container .progress-line {
  height: inherit;
  width: 50%;
  border-radius: inherit;
  background: linear-gradient(90deg, purple, pink, red);
}

.bottom-navButtons {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 40px;
}

.bottom-controls {
  display: flex;
  gap: 25px;
}

#like {
  color: red;
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  margin-left: 20px;
}

#previous {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
}

#play {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
}

#next {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
}

#share {
  color: purple;
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  margin-right: 20px;
}
</style>
