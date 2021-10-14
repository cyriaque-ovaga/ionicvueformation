<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button
            text=""
            color="light"
            :default-href="pageDefaultBackLink"
          ></ion-back-button>
        </ion-buttons>
        <ion-title>{{ pageTitle }} </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <slot />
    </ion-content>
  </ion-page>
</template>

<script>
import {
  IonHeader,
  IonTitle,
  IonToolbar,
  IonPage,
  IonContent,
  IonBackButton,
  IonButtons,
} from "@ionic/vue";
import { defineComponent } from "vue";
export default defineComponent({
  props: ["pageTitle", "pageDefaultBackLink"],
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonPage,
    IonContent,
    IonBackButton,
    IonButtons,
  },
});
</script>
