<template>
    <div>
        <Counter v-for="(item, i) in counterList" :key="i" :count="item.count" :index="i"></Counter>
    </div>
</template>

<script>
    import Counter from './Counter.vue'

    export default {
        name: "CounterGroup",
        props: {
            counterList: Array,
        },
        components: {
            Counter,
        },
    }
</script>

<style scoped>

</style>