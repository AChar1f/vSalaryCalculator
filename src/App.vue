<template>

  <form class="container">
    <h2>Salary Calculator</h2>
    <input type="number" placeholder="Rate" v-model="rate" rate/><label>{{ rate === '' ? '*' : '' }}</label>
    <input type="number" placeholder="Hours" v-model="hours" hours/><label>{{ hours === '' ? '*' : '' }}</label>
    <input type="text" placeholder="First Name" v-model="firstName" firstName/>
    <input type="text" placeholder="Last Name" v-model="lastName" lastName/>
    <textarea output readonly/>
    <button type="button" @click="userInput">Calculate</button>
    <button type="button" @click="clearButton">Clear</button>
  </form>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      rate : '',
      hours : '',
      firstName: '',
      lastName: '',
    }
  },
  methods: {
    userInput() {
      document.querySelector('[output]').textContent = 
      `
      Hello ${this.firstName+" " + this.lastName}, your salary is ${"R" + this.rate * this.hours} 
      `
    },   
    clearButton(){
      document.querySelector('[output]').textContent = ''
      document.querySelector('[rate]').value = ''
      document.querySelector('[hours]').value = ''
    },
    // fieldcheck(){
    //   let spanElement = document.querySelector('[empty]')
    //   if(document.querySelector('[rate]').value === '' && document.querySelector('[hours]').value === ''){
    //       spanElement.textContent = '*'
    //   } else {
    //        spanElement.textContent = ' '
    // }
    // }
  }
}
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
.container{
  display: grid;
  background-color: darkslategrey;
  color: red;
  gap: .8rem;
  width: 30rem;
  margin-inline: auto;
  padding: 1rem;
  & input {
    text-align: center;
    height: 2rem;
    background-color: silver;
  }
  & textarea {
    text-align: center;
    height: 3rem;
    background-color: limegreen;
  }
}
h2 {
  color: black;
}
</style>
