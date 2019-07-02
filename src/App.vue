<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CounterGroup :counter-list="counterList"/>
    <CounterSum :total="total"/>
  </div>
</template>

<script>
import CounterGroup from './components/CounterGroup.vue'
import CounterSum from './components/CounterSum.vue'

export default {
  name: 'app',
  data(){
    return {
      counterList: [{
        count: 0,
      }, {
        count: 0,
      }],
    }
  },
  components: {
    CounterGroup,
    CounterSum,
  },
  computed: {
    total(){
      return this.counterList.reduce((acc, item) => acc+item.count, 0);
    }
  },
  methods: {
    handleIncrease(i) {
      this.counterList[i]++;
    }
  },
  mounted() {
    const that = this;
    this.$root.Bus.$on("increase", i => {
      that.counterList[i].count++;
    });
    this.$root.Bus.$on("decrease", function (i) {
      that.counterList[i].count--;
    })
  },

  beforeDestroy() {
    this.$root.Bus.$off('increase');
    this.$root.Bus.$off('decrease')
  },

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
