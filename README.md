###### We are still working on it. (%60)
# Spotify Filtered Tracs by Language
We have so many playlist in our spotify account. We are listening french, arabic, turkish musics. So we have playlists but we don't have any filter feature about countries or language.

We created a product for spotify filter feature. In this app you will see all tracks in your playlist and you will filtered each song by language.

For now we are just listing your playlists and listing your tracks by playlist. If you want test follow this url. http://spotify.msdeveci.net 

# Installing
If you want working on your localhost you are need change api url.

### Step 1
Go Home.vue and find this row:
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
### Step 2
You should create an app in spotify developers platform and you need take client_id after that you need change login url in Home.vue file. 

You can visit https://developer.spotify.com/dashboard/applications.


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
