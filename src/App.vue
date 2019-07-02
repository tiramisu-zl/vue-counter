<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
<!--    <CounterGroup :counter-list="counterList"/>-->
<!--    <CounterSum :total="total"/>-->
    <Counter :count="count"></Counter>
  </div>
</template>

<script>
import CounterGroup from './components/CounterGroup.vue'
import CounterSum from './components/CounterSum.vue'
import Counter from './components/Counter.vue'

export default {
  name: 'app',
  components: {
    Counter,
  },
  computed: {
    count () {
      return this.$store.state.count
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
