<template>
    <div>
        <div>
            <button @click="displayNormalJoke">Normal Joke!</button>
            <h1>{{normalJoke}}</h1>
        </div>
    </div>
</template>

<script>
    export default {
        name: "NormalJoke",
        data() {
            return {
                normalJoke: ""
            }
        },
        methods: {
            displayNormalJoke(joke) {
                this.normalJoke = joke;
            },
        },
        mounted () {
            this.$root.$on(`displayJoke`, this.displayNormalJoke);
        },
    }
</script>

<style scoped>

</style>