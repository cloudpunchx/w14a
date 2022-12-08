<template>
    <div>
        <button @click="makeSnake">Make Snake!</button>
        <h1>{{snakeJoke.replaceAll('','_')}}</h1>
    </div>
</template>

<script>
    export default {
        name: "SnakeJoke",
        data() {
            return {
                snakeJoke: ""
            }
        },
        methods: {
            makeSnake(snakeJoke) {
                this.snakeJoke = snakeJoke;
            }
        },
        mounted () {
            this.$root.$on(`displayJoke`, this.makeSnake);
        },
    }
</script>

<style scoped>

</style>

<!-- replacement as response to emit -->

<!-- event handler converts to snake -->
<!-- on snake case side, set listener on mounted -->
<!-- function handler will only happen when joke is rec'd -->
<!-- then display result -->
<!-- on click, make another emit that communicates another version of joke to container that displays it -->