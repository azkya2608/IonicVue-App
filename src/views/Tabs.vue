<template>
<ion-page>
    <ion-content>
        <ion-tabs>
            <ion-tab-bar slot="bottom">
                <ion-tab-button tab="tab1" href="/tabs/tab1">
                    <ion-icon :icon="location" />
                    <ion-label>Location</ion-label>
                </ion-tab-button>

                <ion-tab-button tab="tab2" href="/tabs/tab2">
                    <ion-icon :icon="images" />
                    <ion-label>Photos</ion-label>
                </ion-tab-button>

                <ion-tab-button tab="tab3" href="/tabs/tab3">
                    <ion-icon :icon="call" />
                    <ion-label>Phone</ion-label>
                </ion-tab-button>
            </ion-tab-bar>
        </ion-tabs>
    </ion-content>
</ion-page>
</template>

<script lang="ts">
import {
    IonTabBar,
    IonTabButton,
    IonTabs,
    IonContent,
    IonLabel,
    IonIcon,
    IonPage
} from '@ionic/vue';
import {
    images,
    call,
   location
} from 'ionicons/icons';

export default {
    name: 'Tabs',
    components: {
        IonContent,
        IonLabel,
        IonTabs,
        IonTabBar,
        IonTabButton,
        IonIcon,
        IonPage
    },
    setup() {
        return {
            images,
            call,
            location
        }
    }
}
</script>
