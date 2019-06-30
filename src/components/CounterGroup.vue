<template>
    <div>
        <Counter v-for="count in counterNum" :key="count"> {{count}}</Counter>
    </div>
</template>

<script>
    import Counter from './Counter.vue'

    export default {
        name: "CounterGroup",
        props: {
            counterNum: Number,
        },
        components: {
            Counter,
        },
    }
</script>

<style scoped>

</style>