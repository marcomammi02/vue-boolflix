<template>
  <li class="card">
    <ul>
      <li>{{ title }}</li>
      <li>{{ originalTitle }}</li>
      <li>
        <lang-flag
          class="flags"
          :iso="language"
          :title="language"
        />
      </li>
      <li>Vote: {{ ( vote / 2) }}</li>
      <li class="overview">
        {{ overview }}
      </li>
      <li>
        <img
          :src="imgUrlBase + 'w342' + imgUrl"
          :alt="title"
        >
      </li>
    </ul>
  </li>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'CardLayout',
  components: {
    LangFlag,
  },
  props: {
    title: String,
    originalTitle: String,
    language: String,
    vote: Number,
    overview: String,
    imgUrl: String,
  },
  data() {
    return {
      imgUrlBase: 'https://image.tmdb.org/t/p/',
    };
  },
};
</script>

<style lang="scss" scoped>
  * {
    font-size: .85rem;
  }
  .card {
    width: calc((100% / 5) - 1rem);
    height: 330px;
    background-color: rgb(255, 255, 255);
    padding: 1rem;
    border-radius: 10px;
    position: relative;
  }

  .overview {
    overflow: auto;
    max-height: 230px;
  }

  ul {
    list-style: none;
  }

  .flags {
    font-size: 1.5rem;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .card:hover img {
    display: none;
  }
</style>
