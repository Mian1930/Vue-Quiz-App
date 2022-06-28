<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1>
    <h2>{{title}}</h2> -->
    <h3>{{azan}}</h3>
    {{good}}
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // props: {
  //   msg: String,
  //   title:String,
     props:['azan','good']
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
