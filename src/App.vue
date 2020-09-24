<template>
  <div id="app">
    <img alt="Vue logo" src="https://pbs.twimg.com/media/EicU5xaU0AAzWlh.png" width=300px;>
    <Overview />
    <Series />
  </div>
</template>

<script>
import Overview from './components/Overview'
import Series from './components/Series'
export default {
  name: 'App',
  components: {
    Overview,
    Series,
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
