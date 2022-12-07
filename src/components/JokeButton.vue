<template>
    <div>
        <div>
            <!-- button to get joke 1 at a time on click  -->
            <button @click="displayJoke">Get Joke!</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: "JokeButton",
        methods: {
            displayJoke() {
                this.$root.$emit(`displayJoke`);
            }
        },
        mounted () {
            axios.request({
                url: "https://geek-jokes.sameerkumar.website/api?format=json",
                method: "GET"
            }).then((response)=>{
                this.jokes = response.data.joke;
            }).catch((error)=>{
                console.log(error);
            });
        },
    }
</script>

<style scoped>

</style>