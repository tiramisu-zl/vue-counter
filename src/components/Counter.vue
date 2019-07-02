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
            index: Number,
        },
        methods: {
            handleIncrease() {
                // this.count++;
                this.$root.Bus.$emit('increase', this.index);
            },
            handleDecrease() {
                // this.count--;
                this.$root.Bus.$emit('decrease', this.index);
            }
        }
    }
</script>

<style scoped>

</style>