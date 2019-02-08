<template>
    <div id="components" class="form">
        <label for="CampaignName">Nom de la Campagne</label>
        <input v-model="nametoadd">
        <button v-on:click="addName">Ajouter</button><br><br>

        <label for="Keywords">Mots-clé</label>
        <input v-model="keytoadd">
        <button v-on:click="addKeyword">Ajouter</button><br><br>
        <p>Nom de la campagne : {{list.name}}</p>
        <ul>
            <li v-for="(keyword,index) in list.keywords" v-bind:key="index">
                {{keyword}} <button v-on:click="remove(index)">Supprimer</button>
            </li>
        </ul>
        <button v-on:click="generateJson">Générer JSON</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list:{
                name: "champagne",
                keywords: ["coucou","cmwoi"]
            },
            keytoadd: null,
            nametoadd: null,
            jsonfile: null
        }
    },

    methods: {
        generateJson: function() {
            
        },
        addKeyword: function() {
            this.list.keywords.push(this.keytoadd);
        },
        addName: function() {
            this.list.name = this.nametoadd;
        },
        remove: function(index) {
            this.list.keywords.splice(index, 1)
        },
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