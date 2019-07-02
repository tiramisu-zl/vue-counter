<template>
    <div>
        <button @click="handleIncrease"> + increase </button>
        <button @click="handleDecrease"> - decrease </button>

        <p>the number is {{count}}</p>
    </div>
</template>

<script>
    export default {
        name: "Counter",
        props: {
            count: Number,
        },
        methods: {
            handleIncrease() {
                this.$store.commit('increment')
            },
            handleDecrease() {
                this.$store.commit('decrement')
            }
        }
    }
</script>

<style scoped>

</style>