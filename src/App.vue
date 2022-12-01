<template>
  <div>
    <PageHeader @queryChange="search" />
    <PageMain
      :arr-movies="arrMovies"
      :arr-tv="arrTv"
    />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader.vue';
import PageMain from '@/components/PageMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    PageHeader,
    PageMain,
  },
  data() {
    return {
      baseApiUrl: 'https://api.themoviedb.org/3',
      apiKey: '94658c8e681224e297de49ce3445826b',
      resultsLanguage: 'it-IT',
      arrMovies: [],
      arrTv: [],
    };
  },
  methods: {
    search(value) {
      axios.get(`${this.baseApiUrl}/search/movie`, {
        params: {
          api_key: this.apiKey,
          query: value,
          language: this.resultsLanguage,
        },
      })
        .then((responseAxios) => {
          this.arrMovies = responseAxios.data.results;
          console.log(this.arrMovies);
        });
      axios.get(`${this.baseApiUrl}/search/tv`, {
        params: {
          api_key: this.apiKey,
          query: value,
          language: this.resultsLanguage,
        },
      })
        .then((responseAxios) => {
          this.arrTv = responseAxios.data.results;
          console.log(this.arrTv);
        });
    },
  },
};
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrat', sans-serif;
  }

  body {
    background-color: #3b3b3b;
  }
</style>
