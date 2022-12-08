<template>
    <div>
        <div>
            <!-- This button SHOULD get a Joke using the 'getJoke' method which holds API -->
            <button @click="getJoke">Get Joke!</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: "JokeButton",
        data() {
            return {
                joke: ""
            }
        },
        methods: {
            // getJoke triggered by @click on button above
            getJoke(){
                axios.request({
                url: "https://geek-jokes.sameerkumar.website/api?format=json",
                method: "GET"
            }).then((response)=>{
                // I want THIS.joke(my key value in return-data) to become response.data.joke (taken from API call)
                this.joke = response.data.joke;
                // then I want to EMIT the name 'displayJoke', arg= this.joke
                this.$root.$emit(`displayJoke`, this.joke);
            }).catch((error)=>{
                console.log(error);
            });
            }
        },
    }
</script>

<style scoped>

</style>