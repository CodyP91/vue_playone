<template>
  <div>
    <h2>Songs</h2>
    <ul>
      <li v-for="song in songs" :key="song.songid" @click="selectSong(song)">
        <img :src="song.imageurl" :alt="song.title">
        <div>
          <h3>{{ song.title }}</h3>
          <p>{{ song.artist }}</p>
        </div>
      </li>
    </ul>
    <div v-if="currentSong">
      <h2>Playing Song</h2>
      <img :src="currentSong.imageurl" :alt="currentSong.title">
      <div>
        <h3>{{ currentSong.title }}</h3>
        <p>{{ currentSong.artist }}</p>
      </div>
    </div>
    <div v-else>
      <p>Please select a song to play.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      songs: [
        {
          title: "Song 1",
          artist: "Artist 1",
          songid: 1,
          imageurl: "https://via.placeholder.com/150"
        },
        {
          title: "Song 2",
          artist: "Artist 2",
          songid: 2,
          imageurl: "https://via.placeholder.com/150"
        },
        {
          title: "Song 3",
          artist: "Artist 3",
          songid: 3,
          imageurl: "https://via.placeholder.com/150"
        }
      ],
      currentSong: null
    };
  },
  methods: {
    selectSong(song) {
      this.currentSong = song;
    }
  }
};
</script>

<style>
ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
}
li {
  display: flex;
  align-items: center;
  margin-right: 1rem;
  margin-bottom: 1rem;
  cursor: pointer;
}
li:hover {
  background-color: #eee;
}
img {
  width: 100px;
  height: 100px;
  margin-right: 1rem;
}
</style>
