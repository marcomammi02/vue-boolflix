<template>
  <div>
    <PageHeader />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader.vue';

export default {
  name: 'App',
  components: {
    PageHeader,
  },
};
</script>

<style>
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
