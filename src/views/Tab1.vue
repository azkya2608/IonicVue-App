<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Location</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true" >
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Location</ion-title>
        </ion-toolbar>
      </ion-header>
      <p align="center">My Location is: {{loc}}</p>
      <ion-button vertical="bottom" horizontal="center" expand="block" shape="round" fill="outline" @click="getlocation()">Where am I</ion-button>
    
     
    </ion-content>
  </ion-page>
</template>
<style>
p {

color:black;
  text-indent: 30px;
  text-transform: camelcase;

}
</style>

<script lang="ts">
import { ref } from 'vue';
import { Plugins } from '@capacitor/core';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton } from '@ionic/vue';


export default  {
  name: 'Tab1',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonButton },
  setup() {

    const loc = ref({});
    const getlocation = async() => {
          const { Geolocation } = Plugins;
          const res = await Geolocation.getCurrentPosition();
          loc.value = { lat: res.coords.latitude, long: res.coords.longitude }
    }
    return{
      loc,
      getlocation
    };
    
  }
  
}

</script>