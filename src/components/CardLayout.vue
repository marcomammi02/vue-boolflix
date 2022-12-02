<template>
  <li class="card">
    <ul>
      <li>{{ title }}</li>
      <li>{{ originalTitle }}</li>
      <li>{{ language }}</li>
      <li>{{ vote }}</li>
      <li class="overview">
        {{ overview }}
      </li>
    </ul>
  </li>
</template>

<script>

export default {
  name: 'CardLayput',
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
</style>
