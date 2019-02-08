<template>
    <div id="components" class="form">
        <label for="CampaignName">Nom de la Campagne</label><br>
        <input v-model="list.name">
        <button v-on:click="addKeyword">Ajout Mots-clé</button><br><br>
        <!-- <p>name : {{ list.name }}</p> -->
        <span>Entrer les mots-clés</span><br>
        <textarea rows="6" cols="40" v-model="list.keywords"></textarea><br>
        <ul>
            <li v-for="(keyword,index) in list.keywords" v-bind:key="index">{{keyword}}</li>
        </ul>
        <!-- <p>keywords : {{ list.keywords }}</p> -->
        <button v-on:click="generateJson">Générer JSON</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list:{
                name: "coucou",
                keywords: ["coucou","cucu"]
            }
        }
    },

    methods: {
        generateJson: function() {
            
        },
        addKeyword: function() {
            this.list.keywords.push(this.list.name);
        }
    }
}
</script>

<style>
    li{
        text-align: left;
        padding: 10px;
    }
    ul{
        margin-left : auto;
    }
</style>