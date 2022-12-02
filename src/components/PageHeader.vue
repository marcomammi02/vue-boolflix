<template>
  <div class="header">
    <h1>Bool-Flix</h1>
    <form @submit.prevent="$emit('queryChange', quaryString)">
      <label for="quary">
        <input
          id="quary"
          v-model="quaryString"
          type="text"
          name="quary"
          placeholder="Search movies or series..."
        >
      </label>
      <button>Search</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'PageHeader',
  data() {
    return {
      quaryString: '',
    };
  },

};
</script>

<style lang="scss" scoped>
  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 0;
    background-color: #000000;
  }

  h1 {
    color: #ff0000;
    font-size: 2.5rem;
    margin-left: 2.5rem;
    font-family: 'Zen Dots', cursive;
  }

  form {
    margin-right: 2.5rem;
  }

  input {
    width: 200px;
    height: 28px;
  }

  button {
    width: 60px;
    height: 28px;
    color: #ffffff;
    background-color: #ff0000;
    border: none;
  }

</style>
