<template>
  <div>
    <h1 style="text-align: left;padding: 0 40px;font-size: 40px;color: white;display: flex;flex-direction: column;width: 100%;justify-content: space-between;box-sizing: border-box;">
      <strong style="text-align: center;font-size: 50px;font-weight: 900" v-if="playlists.length===0">Can you login?</strong>
      <p v-if="playlists.length===0" style="font-size: 20px;margin-top: 5px; text-align: center;">We need authorization for get your playlists in your spotify account.</p>
      <strong v-else style="font-size: 50px;">Your Playlists. <strong style="font-size: 17px;font-weight: 500;opacity: .5;float: right;height: 68px;display: flex;align-items: center;text-align: right">You need choose a playlist for listing <br /> by countries of songs.</strong></strong>
    </h1>
    <section v-if="playlists.length===0" style="">
      <a
        class="button"
        href="https://accounts.spotify.com/authorize?
            client_id=d70e95faf5884760a307338f6ff01288
            &redirect_uri=http://spotify.msdeveci.net
            &scope=playlist-read-private
            &response_type=token"
      >
        LOGIN WITH SPOTIFY
      </a>
    </section>
    <section v-else class="list-of-playlists">
      <div v-for="p in playlists">
        <router-link :to="`/detail/${p.id}`">
        </router-link>
        <figure>
          <img :src="p.images[0].url" alt="image">
        </figure>
        <h1>{{p.name}}</h1>
      </div>
    </section>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'home',
  data() {
    return {
      playlists: [],
    };
  },
  methods: {
    getPlaylists() {
      axios
        .get('https://api.spotify.com/v1/me/playlists', {
          headers: {
            'Content-Type': 'application/x-www-form-urlencoded',
            Authorization: `Bearer ${localStorage.access_token.split('&')[0]}`,
          },
          json: true,
        })
        .then((response) => {
          this.playlists = response.data.items;
          // response.data.items.forEach((e) => {
          //   axios
          //     .get(`https://api.spotify.com/v1/playlists/${e.id}/tracks`, {
          //       headers: {
          //         'Content-Type': 'application/x-www-form-urlencoded',
          //         Authorization: `Bearer ${localStorage.access_token.split('&')[0]}`,
          //       },
          //       json: true,
          //     })
          //     .then((r) => {
          //       this.playlists.push(r.data.items);
          //     });
          // });
        });
    },
  },
  created() {
    this.getPlaylists();
  },
};
</script>

<style>
  .list-of-playlists {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    border-top: 1px solid #282828;
  }
  .list-of-playlists div {
    position: relative;
  }


  .list-of-playlists a {
    position: absolute;
    width: 100%;
    height: 100%;
    background: red;
    top: 0;
    left: 0;
    opacity: 0;
  }
  .list-of-playlists div {
    flex: 0 0 20%;
    max-width: 20%;
    padding: 50px;
    border-right: 1px solid #282828;
    box-sizing: border-box;
    border-bottom: 1px solid #282828;
  }

  .list-of-playlists div figure {
    width: 100%;
    margin: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .list-of-playlists div figure img {
    max-height: 170px;
    width: auto;
  }

  body {
    margin: 0;
  }

  .list-of-playlists div h1 {
    margin-bottom: 0;
    color: #3e3435;
    font-size: 20px;
  }

  .list-of-playlists div:hover {
    background: rgba(38, 31, 32, 0.26);
    cursor: pointer !important;
  }
  .list-of-playlists div * {
    cursor: pointer;
  }
</style>
