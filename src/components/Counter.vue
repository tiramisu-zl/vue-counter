<template>
    <div>
        <button v-on:click="counter += 1"> + increase </button>
        <button v-on:click="counter -= 1"> - decrease </button>

        <p>the number is {{counter}}</p>
    </div>
</template>

<script>
    export default {
        name: "Counter",
        data() {
            return {
                counter: 0
            }
        }
    }
</script>

<style scoped>

</style>