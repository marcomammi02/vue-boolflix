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
      <li>{{ vote }}</li>
      <li class="overview">
        {{ overview }}
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
  }

  .overview {
    overflow: auto;
  }

  ul {
    list-style: none;
  }

  .flags {
    font-size: 1.5rem;
  }
</style>
