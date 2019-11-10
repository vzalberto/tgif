<template>
  <div id="app">
    <TGIF :gifs=gifs.data />
  </div>
</template>

<script>
import TGIF from './components/TGIF.vue'
import axios from 'axios'

const GIPHY_URL = "https://api.giphy.com/v1/gifs/search?api_key=KQzPKVUFZUIpii6iYFGNphMc7ujV6UcR&q=TGIF&rating=G&limit=5"

export default {
  name: 'app',

  data () {
    return {
      gifs : []
    }
  },

  components: {
    TGIF
  },

  beforeMount () {
      axios
        .get(GIPHY_URL)
        .then(res => this.gifs = res.data)
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
