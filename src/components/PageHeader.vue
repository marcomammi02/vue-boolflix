<template>
  <div>
    <h1>Bool-Flix</h1>
    <label for="search">
      <input
        id="search"
        type="text"
        placeholder="Search movies or series..."
      >
      <button>Search</button>
    </label>
  </div>
</template>

<script>
export default {

};
</script>

<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css2?family=Zen+Dots&display=swap');

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

  label {
    margin-right: 2.5rem;
  }

  input {
    width: 200px;
    height: 28px;
  }

  button {
    width: 60px;
    height: 28px;
  }

</style>
