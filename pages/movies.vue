<template>
  <div class="wrapper">
  <imageHeader></imageHeader>
    <h1 class="heading">Movie Recs</h1>
    <section class="container" v-if="moviedata">  
        <card
          v-for="movie of moviedata"
          :key="movie.Title"
          :movie="movie"
        /> 
    </section>
    <footerNormal></footerNormal>
  </div>
</template>

<script>
import imageHeader from '../components/imageHeader.vue'
import footerNormal from '../components/footerNormal.vue'
import Card from '../components/image-card.vue'
import axios from 'axios'
export default {
  components: {
    Card
  },
  data() {
    return {
      loading: true,
      moviedata: null,
      errored: false
    }
  },
  mounted () {
  axios
    .get('http://www.omdbapi.com/?s=kids&apikey=3e2785f0')
    // .then(response => (console.log(response.data.Search)))
    .then(response=> (this.moviedata=response.data.Search))
    .then(response=>console.log(this.moviedata))
 
    
    
    
    .catch(error => {
      console.log(error)
      this.errored = true
    })
    .finally(() => this.loading = false)
  }
  
}
</script>

<style>
.container {
  min-height: 100vh;
  max-width: 1200px;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  text-align: center;
  flex-wrap: wrap;
}
.heading {
  text-align: center;
  font-size: 2rem;
  color: #555;
  margin: 2rem auto;
}
img {
  max-width: 150px;
}
.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.links {
  padding-top: 15px;
}
</style>