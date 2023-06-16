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
    <div class="div-pad">
        <button @click="increment" id="first" class="rounded-full border-2 border-slate-50">Get ship information!</button>
        <p> Hi this is home :) </p>
        <p>The counter is at: {{ count }}</p>
        <h1 className="text-3xl font-bold underline"> Yoooo </h1>
    </div>
    
</template>