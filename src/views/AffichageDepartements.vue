<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title style="text-align: center; color: #3dc2ff">RD</ion-title>
      </ion-toolbar>
    </ion-header>

<ion-content>
    <form @submit="showdepa">
      <ion-col>
        <ion-item>
          <ion-label>Département</ion-label>

          <ion-select placeholder="Sélectionner"  v-model="dep" id="selectedOption" @select="dep= $event.target.value">
            <ion-select-option
                    v-for="(r) in result"
                    :key="r.code"
                    :value="r.code" >
                    {{r.code}}-{{r.nom}}
          </ion-select-option>
          </ion-select>
        </ion-item>
         </ion-col>
      <ion-col>
        <ion-button type="submit" color="dark" expand="block">Recherche</ion-button>
      </ion-col>
    </form>

<ion-content>
  <ion-list>
    <ion-item v-for="(s) in selected" :key="s.nom">
      <p><ion-card-title>{{s.nom}} </ion-card-title><br>code postal : {{s.codes}} <br>population : {{s.population}}</p>
    </ion-item>
  </ion-list>
</ion-content>

</ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle } from '@ionic/vue';
import axios from "axios";

export default  {
  name: 'AffichageDepartements',
  components: { IonHeader, IonToolbar, IonTitle, IonPage },

  data() {
    return {
      dep: "",
      result: null,
      selected: null
    }
  },

  mounted() {
      axios.get(`https://geo.api.gouv.fr/departements`)
              .then((response) => {
                response.data;
                this.result = response.data;
                console.log(this.result)
         });
    },

      methods: {
        showdepa(e) {
          e.preventDefault()
          // eslint-disable-next-line no-undef
          axios.get('https://geo.api.gouv.fr/departements/'+selectedOption.value+'/communes')
                  .then((response) => {
                    response.data;
                    this.selected = response.data;
                    //console.log(this.selected[0].nom)
             });
        },
      }
};
</script>