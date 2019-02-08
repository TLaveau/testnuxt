<template>
    <div id="components" class="form">
        <label for="CampaignName">Nom de la Campagne</label>
        <input v-model="nametoadd">
        <button v-on:click="addName">Ajouter</button><br><br>

        <label for="Keywords">Mots-clé</label>
        <input v-model="keytoadd">
        <button v-on:click="addKeyword">Ajouter</button><br><br>
        <p>Nom de la campagne : {{list.campaigns.name}}</p>
        <ul>
            <li v-for="(keyword,index) in list.campaigns.keywords" v-bind:key="index">
                {{keyword}} <button v-on:click="remove(index)">Supprimer</button>
            </li>
        </ul>
        <button v-on:click="generateJSON">Générer JSON</button>
        <p>JSON : {{ jsonfile }}</p>
        <button v-on:click="generateCSV">Générer CSV</button>
        <p>CSV : {{ csvfile }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list:{
                campaigns: {
                    name : "champagne",
                    keywords: ["coucou","cmwoi"]
                }
            },
            keytoadd: null,
            nametoadd: null,
            jsonfile: null,
            csvfile: null
        }
    },

    methods: {
        generateJSON: function() {
            const data = JSON.stringify(this.list)
            this.jsonfile = data;
            const blob = new Blob([data], {type: 'text/plain'})
            const e = document.createEvent('MouseEvents'),
            a = document.createElement('a');
            var jsonName = "campagne" + this.list.campaigns.name;
            a.download = jsonName + ".json";
            a.href = window.URL.createObjectURL(blob);
            a.dataset.downloadurl = ['text/json', a.download, a.href].join(':');
            e.initEvent('click', true, false, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);
            a.dispatchEvent(e);
        },
        generateCSV: function() {
            var csv = "";
            csv = "campaigns,keywords" + '\r\n';
            csv += this.list.campaigns.name + "," + '\r\n';
            this.list.campaigns.keywords.forEach(element => {
                csv += this.list.campaigns.name + "," + element + '\r\n';
            });
            this.csvfile = csv;

            // Download file
            const blobcsv = new Blob([csv], {type: 'text/plain'})
            const ecsv = document.createEvent('MouseEvents'),
            a = document.createElement('a');
            var csvName = "campagne" + this.list.campaigns.name;
            a.download = csvName + ".csv";
            a.href = window.URL.createObjectURL(blobcsv);
            a.dataset.downloadurl = ['text/csv', a.download, a.href].join(':');
            ecsv.initEvent('click', true, false, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);
            a.dispatchEvent(ecsv);
        },
        addKeyword: function() {
            this.list.campaigns.keywords.push(this.keytoadd);
        },
        addName: function() {
            this.list.campaigns.name = this.nametoadd;
        },
        remove: function(index) {
            this.list.campaigns.keywords.splice(index, 1)
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