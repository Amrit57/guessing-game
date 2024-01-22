<template>
  <div class="container">
    <h1 class="mb-4 text-center">Guess the country and It's capital city</h1>
    <h3 class="text-center mt-4">{{ result }}</h3>
    <p class="mx-auto text-center">{{ selectedMessage1 }}</p>
    <p class="mx-auto text-center">{{ selectedMessage2 }}</p>
    <h3 class="error text-center">{{ error }}</h3>
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
      selectedMessage1: '',
      selectedMessage2: '',
      result:'',
      error:''
    }
  },
  methods: {
    selectCountry(item) {
      this.selectedCountry = item.country
      this.selectedMessage1 = `Country =  ${this.selectedCountry}`
      this.result = ''
      this.error=''

    },
    selectCity(item) {
      this.selectedCity = item.capital
      this.error=''
      this.result = ''
      this.selectedMessage2 = `Capital City = ${this.selectedCity}`


    },
    checkAnswer() {
      if (this.selectedCity && this.selectedCountry) {

        const selectCityIndex = this.globalData.findIndex(item => item.capital === this.selectedCity);
        const selectCountryIndex = this.globalData.findIndex(item => item.country === this.selectedCountry)


        if (selectCountryIndex !== -1 && selectCityIndex !== -1 && selectCountryIndex === selectCityIndex) {
          this.result= `Correct Answer!!!`
        } else {
          this.result= `Incorrect, Please try again!!!`
        }

        this.selectedCity = null,
          this.selectedCountry - null
      } else {
          this.error = ('Please select new country and city')
      }
    }
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
.error{
  color: red;
}
</style>