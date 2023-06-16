<script>
//const axios = require('axios');

import axios from 'axios';

//cli = process.env.local.TOKEN
var token = import.meta.env.ST_TOKEN1;

const options = {
    method: 'GET',
    url: 'https://api.spacetraders.io/v2/',
    headers: { Accept: 'application/json', Authorization: token }
};


export default {
    data() {
        return {
            info: null,
        }
    },

    methods: {
        async increment() {
            try {
                const data = await axios.request(options);
                console.log(data.data.status);
                this.info = data;
                // response.then(res => console.log(res));
                // update(response);
            } catch (error) {
                console.error(error);
            }
        }
    },

    mounted() {
        console.log(`Count up! Count is at: ${this.count}!`)
    }
}
</script>

<template>
    <p> Hi this is ships :) </p>
     <button @click="increment" id="first" class="rounded-lg border-2 border-slate-50 p-1"> Get ship information!</button>
            <p>Here: {{ info }}</p>
</template>