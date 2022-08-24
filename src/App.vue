<template>
  <div>
    <BaseHeader @my-search="myQuery" />
    <TheMain :movies="movies" :tvShows="tvShows" />

  </div>
</template>

<script>
import axios from 'axios'
import BaseHeader from './components/BaseHeader.vue'
import TheMain from './components/TheMain.vue'

export default {
  name: 'App',
  components: {
    BaseHeader,
    TheMain,
  },
  data() {
    return {
      movies: [],
      tvShows: [],

      apiKey: '13f9d49016c328edde12db1ecea56457',
      query: ''
    }
  },
  methods: {
    myQuery(query) {
      this.query = query
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&query=${this.query}`).then((res) => {
        this.movies = res.data.results
      })
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&query=${this.query}`).then((res) => {
        this.tvShows = res.data.results
      })
    },
  },
}



</script>

