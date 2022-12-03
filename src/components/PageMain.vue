<template>
  <div class="main">
    <h2 v-if="(arrMovies.length > 0)">
      Movies
    </h2>
    <ul class="container">
      <CardLayout
        v-for="objMovie in arrMovies"
        :key="objMovie.id"
        :title="objMovie.title"
        :original-title="objMovie.original_title"
        :language="objMovie.original_language"
        :vote="objMovie.vote_average"
        :overview="objMovie.overview"
        :img-url="objMovie.poster_path"
      />
    </ul>

    <h2 v-if="(arrTv.length > 0)">
      TV series
    </h2>
    <ul class="container">
      <CardLayout
        v-for="objTv in arrTv"
        :key="objTv.id"
        :title="objTv.name"
        :original-title="objTv.original_name"
        :language="objTv.original_language"
        :vote="objTv.vote_average"
        :overview="objTv.overview"
        :img-url="objTv.poster_path"
      />
    </ul>
  </div>
</template>

<script>
import CardLayout from '@/components/CardLayout.vue';

export default {
  name: 'PageMain',
  components: {
    CardLayout,
  },
  props: {
    arrMovies: Array,
    arrTv: Array,
  },
};
</script>

<style lang="scss" scoped>
  h2 {
    margin: 2rem 0 1rem;
    font-size: 1.8rem;
    text-align: center;
    font-family: 'Zen Dots', cursive;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    flex-basis: 0 0 0;
  }

  ul {
    list-style: none;
  }
</style>
