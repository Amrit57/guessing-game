<template>
  <div class="container">
    <h1 class="m-2">Guess the country and It's capital city</h1>
    <h2 class="m-4">Countries</h2>
    <div>
      <button @click="selectCountry(item)" v-for="(item, index) in globalData" :key="index" class="m-2 btn btn-primary">{{
        item.country }}</button>
    </div>
    <h2 class="m-4">Capital Cities</h2>
    <div>
      <button @click="selectCity(item)" v-for="(item, index) in globalData" :key="index" class="m-2 btn btn-secondary">{{
        item.capital }}</button>
    </div>


    <button @click="checkAnswer" class="btn btn-success m-4">Check Answer</button>
  </div>
</template>

<script>
export default ({
  name: 'App',
  data() {
    return {
      globalData: [
        { country: 'Nepal', capital: 'Kathmandu' },
        { country: 'Japan', capital: 'Tokyo' },
        { country: 'USA', capital: 'Washington, D.C.' },
        { country: 'Canada', capital: 'Ottawa' },
        { country: 'Germany', capital: 'Berlin' },
        { country: 'France', capital: 'Paris' },
        { country: 'Brazil', capital: 'Brasília' },
        { country: 'India', capital: 'New Delhi' },
        { country: 'China', capital: 'Beijing' },
        { country: 'Australia', capital: 'Canberra' },
        { country: 'South Africa', capital: 'Pretoria' },
      ],
      selectedCountry: '',
      selectedCity: '',
    }
  },
  methods: {
    selectCountry(item) {
      this.selectedCountry = item.country
      console.log(this.selectedCountry)
    },
    selectCity(item) {
      this.selectedCity = item.capital
      console.log(this.selectedCity)

    },
    
  }
})
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;

}
</style>