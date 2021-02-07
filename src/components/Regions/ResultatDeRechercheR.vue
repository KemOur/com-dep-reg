<template>
    <ion-content>
        <ion-list>
            <ion-item v-for="(s) in selected" :key="s.nom">
                <p><ion-card-title>{{s.nom}} </ion-card-title><br>code départemental : {{s.code}}</p>
            </ion-item>
        </ion-list>
    </ion-content>
</template>

<script>
    export default {
        name: "ResultatDeRechercheR",
        props: ["selected"]
    }
</script>