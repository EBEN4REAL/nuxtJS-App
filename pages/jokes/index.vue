<template>
    <div>
       Jokes
    </div>
    
</template>

<script>
    import axios from 'axios';
    export default {
        data() {
            return {
                jokes: []
            }
        },
        async  created() {
            const config = {
                headers: {
                    'Accept': 'application/json'
                }
            }

            try{
                const res = await axios.get("https://icanhazdadjoke.com/search", config);
                console.log(res.data);
            }catch (err) {
                console.log(err);
            }
            
        },
        head() {
            return {
                title: 'Dad Jokes',
                meta: [
                    {
                        hid: "description",
                        name: "description",
                        content: "Best place for corny dad Jokes"
                    }
                ]
            }
        }
    }

</script>

<style>

</style>