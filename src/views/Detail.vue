<template>
  <div class="about">
    <router-link to="/"><button class="button" href="">BACK TO PLAYLISTS</button></router-link>
    <div v-for="t in tracks" class="list-in-tracks">
      <h1 style="position:relative;" v-on:click="getLanguage(t.track.name)"><span style="font-size: 12px; top: -15px; position: absolute;">{{t.track.id}}</span>{{t.track.name}} - {{t.track.artists[0].name}}</h1>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'home',
  data() {
    return {
      tracks: [],
    };
  },
  methods: {
    getTracksById() {
      axios
        .get(`https://api.spotify.com/v1/playlists/${this.$route.params.id}/tracks`, {
          headers: {
            'Content-Type': 'application/x-www-form-urlencoded',
            Authorization: `Bearer ${localStorage.access_token.split('&')[0]}`,
          },
          json: true,
        })
        .then((response) => {
          this.tracks = response.data.items;
        });
    },
    getLanguage(name) {
      // We are still working on this row.
      axios
        .get(`http://www.pvcbakimonarim.com/api/getlang?id=${name}`)
        .then((response) => {
        });
    },
  },
  created() {
    this.getTracksById();
  },
};
</script>
