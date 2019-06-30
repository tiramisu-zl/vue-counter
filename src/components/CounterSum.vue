<template>
    <p ref="test">counter in total {{total}}</p>
</template>

<script>
    export default {
        name: "CounterSum",
        data: function () {
            return {
                total: 0,
            }
        },
        mounted() {
            this.$root.Bus.$on("counterChange", val => {
                this.total = val;
            })
        }

    }
</script>

<style scoped>

</style>