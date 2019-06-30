<template>
    <div>
        <button @click="handleIncrease"> + increase </button>
        <button @click="handleDecrease"> - decrease </button>

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
        },
        methods: {
            handleIncrease: function() {
                this.counter++;
            },
            handleDecrease: function() {
                this.counter--;
            }
        }
    }
</script>

<style scoped>

</style>