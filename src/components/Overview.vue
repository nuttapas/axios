<template>
    <div>
        <ul>
          <li v-for="series in serieslist" :key="series.id">
            id {{series.id}} : {{series.title}} 
            <img :src="series.thumbnailUrl">
          </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios'

export default {
    data(){
        return{
            serieslist: null,
            errored: false,
            loading: false,
        }
    },

    mounted(){
        axios
        .get('https://api.themoviedb.org/3/search/tv?api_key=aaf4e31fa3a5803c52aabf3cfde977fc&language=en-US&page=1&query=')
      .then(response => {
        this.serieslist = response.data

      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
      
    },

}
</script>
<style>
    
</style>