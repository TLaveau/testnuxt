<template>
    <div id="components" class="form">
        <span>Campaign name</span><br>
        <input v-model="list.name"><br><br>
        <!-- <p>name : {{ list.name }}</p> -->
        <span>Enter the keywords</span><br>
        <textarea rows="6" cols="40" v-model="list.keywords"></textarea><br>
        <!-- <p>keywords : {{ list.keywords }}</p> -->
        <button v-on:click="json">Generate JSON</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list: [
                {
                    name: null
                },
                {
                    keywords: []
                }
            ]
        }
    },

    methods: {
        json: function() {
            
        }
    }
}
</script>

<style>
</style>