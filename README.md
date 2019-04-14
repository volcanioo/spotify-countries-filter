###### We are still working on it. (%60)
# Filter Tracks by Language on Spotify!
Everybody has their own playlists on Spotify. We listen to the music in different languages like French, Arabic, Turkish, etc.
We experience the lack of filtering the music based on a country or a language on Spotify, so we intended to develop a 3rd party application to serve a filtering feature.

With this web application, you may list all the tracks in a playlist and filter them by language.

For now, we just list the playlist by default. To test our application you may visit our demo page http://spotify.msdeveci.net 

# Installing
If you want to work on your own machine you need to configure API URL based on your own web servers.


### Step 1

You should create an app on Spotify Developers Platform to gain your own credentials. Find the documentation on https://developer.spotify.com/dashboard/applications.

### Step 2
On Home.vue file find this row anc change it with your own credentials
```html
<a
    class="button"
    href="https://accounts.spotify.com/authorize?
            client_id=_CLIENT_ID_
            &redirect_uri=http://localhost:_YOUR_PORT_
            &scope=playlist-read-private
            &response_type=token"
>
    LOGIN WITH SPOTIFY
</a>
```


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Credits
- [Volkan Deveci.](https://twitter.com/volcanioo) Frontend Issues - html, css, js
- [Enes İnkaya.](https://www.linkedin.com/in/enes-inkaya-8811b4b5/) Back-end and Test Issues - php
- [Bora Açıcı.](https://www.linkedin.com/in/boraacici/) Back-end Issues - c#


