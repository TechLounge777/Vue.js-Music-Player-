<template>
  <audio v-bind:src="song.songSrc" preload="auto" autoplay ref="audioPlayer" />
  <div class="top-nav">
    <div id="top-nav-controls">
      <button type="button" id="repeat">
        <i id="sync" class="fas fa-sync"></i>
      </button>

      <button id="redo">
        <i class="fas fa-redo"></i>
      </button>
      <button id="random"><i class="fas fa-random"></i></button>
    </div>
    <div>
      <button @click="gotoplaylist" id="bars">
        <i class="fas fa-bars"></i>
      </button>
    </div>
  </div>
  <div class="cover-photo">
    <img width="380" height="360" alt="icon-pop-cover-photo" />

    <div class="song-info">
      <h1 class="artist" v-bind="$attrs"></h1>
      <h2 class="song-title"></h2>
    </div>
  </div>

  <div class="progress-container">
    <div class="progre ss-line">
      <span></span>
      <div class="timer">
        <span class="current"></span>
        <span class="current"></span>
      </div>
    </div>
  </div>

  <div class="bottom-navButtons">
    <button id="share"><i class="fas fa-share-alt"></i></button>
    <div class="bottom-controls">
      <button @click="previoussong" id="previous">
        <i class="fas fa-step-backward"></i>
      </button>
      <button v-if="!isPlaying" @click="playpauseswitch" id="play">
        <i class="fas fa-play-circle fa-2x"></i>
      </button>

      <button v-if="isPlaying" @click="playpauseswitch" id="pause">
        <i class="fas fa-pause-circle fa-2x"></i>
      </button>
      <button @click="nextsong" id="next">
        <i class="fas fa-step-forward"></i>
      </button>
    </div>
    <button id="like"><i class="fas fa-heart"></i></button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: true,
    };
  },
  props: {
    song: {
      id: Number,
      time: Number,
      artistName: String,
      songTitle: String,
      src: String,
      songSrc: String,
    },
  },
  name: "MusicPlayer",
  emits: ["gotoplaylist", "nextsong", "previoussong"],
  methods: {
    gotoplaylist() {
      this.$emit("gotoplaylist");
    },
    playpauseswitch() {
      if (this.isPlaying) {
        this.$refs.audioPlayer.pause();
      } else {
        this.$refs.audioPlayer.play();
      }
      this.isPlaying = !this.isPlaying;
    },
    nextsong() {
      this.$emit("nextsong");
    },
    previoussong() {
      this.$emit("previoussong");
    },
  },
};
</script>

<style>
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

#repeat {
  background: none;
  border: none;
  color: #fff;
  cursor: pointer;
}

#redo {
  background: none;
  border: none;
  color: #fff;
}

#random {
  background: none;
  border: none;
  color: #fff;
}

#bars {
  display: flex;
  align-items: center;
  padding-top: 30px;
  padding-right: 40px;
  padding-left: 40px;
  color: darkgray;
  background: none;
  border: none;
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
  position: relative;
  border-radius: inherit;
  background: linear-gradient(90deg, purple, pink, red);
}

.progress-line::before {
  content: "";
  position: absolute;
  height: 12px;
  width: 12px;
  background-color: darkred;
  border-radius: inherit;
  top: 50%;
  right: -5px;
  transform: translateY(-50%);
  background: inherit;
  opacity: 0;
  transition: opacity 0.2s ease;
}

.progress-container:hover .progress-line::before {
  opacity: 1;
}

.bottom-navButtons {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 40px;
}

.bottom-controls {
  display: flex;
  align-items: center;
  gap: 25px;
}

#like {
  color: red;
  background-color: seashell;
  padding: 6px;
  height: 50%;
  border-radius: 50%;
  border-style: none;
  margin-left: 15px;
}

#previous {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  height: 50%;
  border-style: none;
}

#play {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  border-style: none;
}

#pause {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  border-style: none;
}

#next {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  height: 50%;
  border-style: none;
}

#share {
  color: purple;
  background-color: seashell;
  padding: 6px;
  height: 50%;
  border-radius: 50%;
  border-style: none;
  margin-right: 15px;
}
</style>
