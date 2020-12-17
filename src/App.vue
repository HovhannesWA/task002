<template>
  <div id="app">    
    <container />
  </div>
</template>

<script>
import Container from './components/Container'
export default {
  name: 'app',
  components: {
    Container    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  box-sizing: border-box;
  border: 2px solid #00BFFF	;
  width: 500px;
  margin: 100px auto;
  padding: 20px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}
</style>
