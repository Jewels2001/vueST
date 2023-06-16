<script>
export default {
    data() {
        return {
            count: 0
        }
    },

    methods: {
        increment() {
            this.count++;
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
            <p>The counter is at: {{ count }}</p>
</template>