<template>
  <section v-if="!isPlayerVisible" class="playlist">
    <div class="playlist-header">
      <button id="return-icon"><i class="fas fa-undo fa-2x"></i></button>
      <h1>Playlist</h1>
      <i id="empty" class="fas fa-undo fa-2x"></i>
    </div>

    <div v-for="song in list" v-bind:key="song.id" class="playlist-item">
      <div class="left-section">
        <div class="playlist-time-and-artist">
          <p>{{ song.time }}</p>
          <p>|</p>
          <p>{{ song.artistName }}</p>
        </div>
        <p class="song-title">{{ song.songTitle }}</p>
      </div>

      <div class="right-section">
        <div class="playlist-icons">
          <button id="playlist-share-song">
            <i class="fas fa-share-alt"></i>
          </button>
          <button id="playlist-like-song"><i class="fas fa-heart"></i></button>
        </div>
      </div>

      <div class="break">
        <hr />
      </div>
    </div>
  </section>
  <div v-if="isPlayerVisible">
    <MusicPlayer
      v-bind:song="list[currentSongIndex]"
      @gotoplaylist="isPlayerVisible = !isPlayerVisible"
    />
  </div>
</template>

<script>
import MusicPlayer from "./MusicPlayer.vue";
export default {
  data() {
    return {
      isPlayerVisible: true,
      currentSongIndex: 0,
      list: [
        {
          id: 1,
          time: 13,
          artistName: "Icona Pop",
          songTitle: "Still don't know",
          src: "https://picsum.photos/seed/picsum/200/300",
          songSrc:
            "https://music.youtube.com/watch?v=Y0hmruuA4Jw&list=RDAMVMY0hmruuA4Jw",
        },
        {
          id: 2,
          time: 12,
          artistName: "Icona Pop",
          songTitle: "I Love It",
          src: "https://picsum.photos/seed/picsum/200/300",
          songSrc:
            "https://music.youtube.com/watch?v=Y0hmruuA4Jw&list=RDAMVMY0hmruuA4Jw",
        },
        {
          id: 3,
          time: 20,
          artistName: "Icona Pop",
          songTitle: "Girlfriend",
          src: "https://picsum.photos/seed/picsum/200/300",
          songSrc:
            "https://music.youtube.com/watch?v=Y0hmruuA4Jw&list=RDAMVMY0hmruuA4Jw",
        },
        {
          id: 4,
          time: 30,
          artistName: "Icona Pop",
          songTitle: "We Got the World",
          src: "https://picsum.photos/seed/picsum/200/300",
          songSrc:
            "https://music.youtube.com/watch?v=Y0hmruuA4Jw&list=RDAMVMY0hmruuA4Jw",
        },
        {
          id: 5,
          time: 24,
          artistName: "Icona Pop",
          songTitle: "Nights Like This",
          src: "https://picsum.photos/seed/picsum/200/300",
          songSrc:
            "https://music.youtube.com/watch?v=Y0hmruuA4Jw&list=RDAMVMY0hmruuA4Jw",
        },
      ],
    };
  },
  hideIcon: true,
  components: {
    MusicPlayer,
  },
  name: "Playlist",
};
</script>

<style>
.playlist-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  font-size: 16px;
  color: darkslateblue;
}

#return-icon {
  background-color: seashell;
  padding: 6px;
  border-radius: 50%;
  height: 50%;
  border-style: none;
  color: purple;
}

#empty {
  padding: 6px;
  border-radius: 50%;
  height: 50%;
  visibility: hidden !important;
  border-style: none;
}

.playlist-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  padding: 15px;
}

.left-section {
  padding-left: 15px;
}

.playlist-time-and-artist {
  display: flex;
  gap: 6px;
  color: grey;
}

.playlist-song-title {
  display: flex;
  justify-content: flex-start;
  color: darkslateblue;
  font-size: 18px;
  font-weight: 500;
}

.song-title {
  display: flex;
  justify-content: flex-start;
}

.playlist-icons {
  display: flex;
  gap: 15px;
  padding: 15px;
}

#playlist-share-song {
  color: purple;
  border-style: none;
  background: none;
}

#playlist-like-song {
  color: red;
  border-style: none;
  background: none;
}
.breakline {
  display: flex;
  justify-content: flex-end;
}
.break {
  flex-basis: 380px;
  height: 1px;
  padding: 15px;
}
</style>
