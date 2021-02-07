<template>
 <ion-content>
                <ion-list>
                    <ion-item v-for="(s) in selected" :key="s.nom">
                        <p><ion-card-title>{{s.nom}} </ion-card-title><br>code postal : {{s.codes}} <br>population : {{s.population}}</p>
                    </ion-item>
                </ion-list>
 </ion-content>
</template>

<script>
    export default {
        name: "ResultatDeRechercheD",
        props: ["selected"]
    }
</script>