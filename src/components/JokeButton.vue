<template>
    <div>
        <div>
            <!-- button to get joke 1 at a time on click  -->
            <button @click="displayJoke">Get Joke!</button>
            <!-- <div class="myDiv" v-for="(jokes,index) in jokes" :key="index">
                {{jokes}}
            </div> -->
        </div>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: "JokeButton",
        data() {
            return {
                joke: null
            }
        },
        methods: {
            displayJoke() {
                this.$root.$emit(`displayJoke`, this.joke);
            },
        },
        mounted () {
            axios.request({
                url: "https://geek-jokes.sameerkumar.website/api?format=json",
                method: "GET"
            }).then((response)=>{
                this.joke = response.data.joke;
            }).catch((error)=>{
                console.log(error);
            });
        },
    }
</script>

<style scoped>

</style>