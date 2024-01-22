<template>
  <div class="container">
    <h1>Guess the country and It's capital city</h1>
    <h2>Countries</h2>
    <div v-for="item in globalData">
      <button>{{ item.country }}</button>
    </div>
    <h2>Capital Cities</h2>
    <div v-for="item in globalData">
      <button>{{ item.capital }}</button>
    </div>
  </div>
</template>

<script>
export default ({
  name: 'App',
  data() {
    return {
      globalData: [
        { country: 'Nepal', capital: 'Kathmandu' },
        { country: 'Japan', capital: 'Tokyo' }
      ],
    }
  }
})
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>