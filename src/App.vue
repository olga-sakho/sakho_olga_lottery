<template>
  <div id="app">
      <button @click="start"> Запусти лотерею </button>
      <hr>
        <button v-for="random, index in randoms" :key="index">{{random}}</button>  
        <hr>
        <p style="color:red">{{message}}</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      randoms: [],
      message:''
    }
  },
  methods: {
      start: function () {
          this.randoms = []
          this.message = ''
                
                function getRandomIntInclusive(min, max) {
                  return Math.floor(Math.random() * (max - min + 1)) + min;
                }
                let random = getRandomIntInclusive(1,5) 
                let random1 = getRandomIntInclusive(1,5) 
                let random2 = getRandomIntInclusive(1,5)        
        
                this.randoms.push(random, random1, random2)
                console.log(this.randoms)

                let n = this.randoms[0]
                for(var i=1;i<this.randoms.length;i++){
                     if(n === this.randoms[i]&& n === this.randoms[i+1]){
                          this.message = 'Поздравляю, Вы выграли приз! ! !'
                     }
                }        

      }
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
</style>
