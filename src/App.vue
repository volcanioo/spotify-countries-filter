<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  mounted() {
    if (this.$route.path.search('access_token=') !== -1) {
      localStorage.setItem('access_token', this.$route.path.split('access_token=')[1].split('&')[0]);
      this.$router.push('/');
    }
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
div {
  clear: both;
  display: block;
}
body {
  background: #181818;
}
a {
  text-decoration: none;
}
a h1, h1 {
  color: #1ed760;
}
a:hover h1 {
  opacity: .5;
}
html {
  background: #171717;
}
h1 span {
  opacity: 0;
  background: #1ed760!important;
  padding: 4px;
  color: #191515;
  border-radius: 3px;
  line-height: 8px;
}
h1:hover span {
  opacity: 1;
}
.button {
  background: #1cb954;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  border: none;
  color: white;
  outline: none;
  cursor: pointer;
  border-radius: 100px;
  padding: 10px 30px;
  display: flex;
  align-items: center;
  font-size: 14px;
  justify-content: center;
  width: fit-content;
  margin: 30px auto 10px auto;
  font-weight: 900;;
}
.button:hover {
  transform: scale(1.05);
  background: #1ed760;
}
</style>
