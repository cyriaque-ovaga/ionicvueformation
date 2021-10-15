<template>
  <form class="ion-padding" @submit.prevent="submitForm">
    <ion-list>
      <ion-item>
        <ion-label position="floating">Title</ion-label>
        <ion-input type="text" required v-model="memory.title"></ion-input>
      </ion-item>
      <ion-item>
        <ion-thumbnail slot="start">
          <img :src="takenImageUrl" />
        </ion-thumbnail>
        <ion-button type="button" fill="clear" @click="takePhoto">
          <ion-icon slot="start" :icon="camera"></ion-icon>
          Take Photo
        </ion-button>
      </ion-item>

      <ion-item>
        <ion-label position="floating">Description</ion-label>
        <ion-textarea rows="5" v-model="memory.description"></ion-textarea>
      </ion-item>
      <ion-button type="submit" expand="block">
        Save
      </ion-button>
    </ion-list>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import {
  IonList,
  IonItem,
  IonLabel,
  IonInput,
  IonTextarea,
  IonButton,
  IonThumbnail,
  IonIcon,
} from "@ionic/vue";
import { camera } from "ionicons/icons";
import { Camera, CameraResultType, CameraSource } from "@capacitor/camera";

export default defineComponent({
  emits: ["savememory"],
  components: {
    IonList,
    IonItem,
    IonLabel,
    IonInput,
    IonTextarea,
    IonButton,
    IonThumbnail,
    IonIcon,
  },
  data() {
    return {
      memory: {
        id: new Date().toISOString(),
        title: "",
        image: "",
        description: "",
      },
      camera,
      takenImageUrl: null,
    };
  },
  methods: {
    async takePhoto() {
      const photo = await Camera.getPhoto({
        quality: 90,
        allowEditing: true,
        resultType: CameraResultType.Uri,
        source: CameraSource.Camera,
      });

      this.takenImageUrl = photo.webPath;
    },
    submitForm() {
      this.$emit("savememory", this.memory);
      this.$router.replace("/memories");
    },
  },
});
</script>
