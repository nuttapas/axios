<template >
  <div>
    <input type="text" v-model="textSearch " />
    <button @click="searchData()">Search</button>
    <b-card-group columns>
    <b-card 
    v-for="list in serieslist"
    :key="list.original_name"
    :title="list.original_name"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem; background : grey; color: #FFFF "
    class="mb-2"
  >
  <b-text  >
    Vote Average {{list.vote_average}}<br />
    Overview {{list.overview}}<br />
    First date {{list.first_air_date}}
  </b-text>

  </b-card>
    </b-card-group>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      serieslist: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get(
          "https://api.themoviedb.org/3/search/tv?api_key=aaf4e31fa3a5803c52aabf3cfde977fc&language=en-US&page=1&query=" +this.textSearch +'&include_adult=false'
        )
        .then((response) => {
          this.serieslist = response.data.results;
          console.log(this.serieslist)
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
</style>