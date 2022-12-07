<template>
    <div>
        <div>
            <!-- <button @click="displayJoke">Get Joke!</button> -->
            <!-- <h1>{{joke}}</h1> -->
        </div>
    </div>
</template>

<script>
    export default {
        name: "NormalJoke",
        data() {
            return {
                joke: null
            }
        },
        methods: {
            displayJoke(joke) {
                this.joke = joke;
            },
        },
        mounted () {
            this.$root.$on(`displayJoke`, this.joke);
        },
    }
</script>

<style scoped>

</style>