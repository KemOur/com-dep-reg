<template>
    <div id="container">
       <div  v-for="(result, index) in result" :key="index">
       <!-- <div  v-if="result"> -->
            <ion-card>
                <ion-card-header class="md hydrated">
                    <ion-card-title class="ion-text-center md hydrated" role="heading" aria-level="2">{{result}}</ion-card-title>
                </ion-card-header>
            </ion-card>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ResultatDeRecherche",
        props: ["result"]
    }
</script>
