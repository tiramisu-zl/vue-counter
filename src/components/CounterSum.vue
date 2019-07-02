<template>
    <p ref="test">counter in total {{total}}</p>
</template>

<script>
    export default {
        name: "CounterSum",
        props: {
            total: Number,
        }
    }
</script>

<style scoped>

</style>