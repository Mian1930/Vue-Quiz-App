<template>
  <div id="app">
    <Header
      :numCorrect="numCorrect"
      :numTotal="numTotal"
    />
    <b-container class="bv-example-row">
  <b-row>
    <b-col sm="6" offset="3">
<QuestionBox
:currentQuestion="questions[index]"
:next="next"
:increment="increment"

/>
    </b-col>
  </b-row>
</b-container>
    
    <!-- <div>
  <b-button>Button</b-button>
  <b-button variant="danger">Button</b-button>
  <b-button variant="success">Button</b-button>
  <b-button variant="outline-primary">Button</b-button>
</div> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>
    <HelloWorld title="welcome to vue js using props"/> -->
    <!-- <HelloWorld azan="hello"/>
    <HelloWorld  azan ="ddd"/> -->
    <!-- <h1>{{name}}</h1>
    <input v-model="azan">
    <div v-if="count ===1">
      Red
    </div>
    <div v-else-if="count ===2">
      orange
    </div>
    <div v-else>
    green
    </div>
    <div v-show="count ===1">
      noob
    </div>
    <input v-model="azan" :style="{color:red}">
    <br>
    <button onclick="alert('signed up')" v-bind="[name.length] >2">sumbit</button>
    <li v-for="car in cars" :key="car">{{car}}</li>
    <input v-model="newCat" v-on:keyup.enter="addName">
    <button v-on:click="addName">
      add+
    </button>
    {{carName}}
    <b-button type="is-primary">Primary</b-button>
            <b-button type="is-primary is-light">Primary Light</b-button> -->
  </div>
  

</template>

<script>

// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import QuestionBox from './components/QuestionBox.vue'
export default {
  name: 'App',
  components: {
    Header,
    QuestionBox
    // HelloWorld
  },
  mounted: function(){
fetch('https://opentdb.com/api.php?amount=10&category=27&type=multiple',{
method:'get'
})
.then((response)=>{
  return response.json()
})
.then((jsonData)=>{
this.questions=jsonData.results
})
},
methods:{
next(){
  this.index++
},
increment(isCorrect) {
      if (isCorrect) {
        this.numCorrect++
      }
      this.numTotal++
    }
},
  data(){
    return{
questions:[],
index:0,
 numCorrect: 0,
      numTotal: 0,
      // name:"azan",
      // azan:"hello",
      // count :1,
      // red:"green",
      // cars:[
      // 'honda',
      //  'nissan',
      // ],
      // newCat:''
    }

  },
  //  methods : {
  //  addName:function(){
  //   return this.cars.push({name:this.newCat})
  //  }
  //  }, 
// computed: {
//   carName:function(){
//     if(this.newCat.length){
//       return this.newCat + 'y'
//     } else {
//       return ''
//     }
//   }
// }
}
</script>
<style >

</style>
