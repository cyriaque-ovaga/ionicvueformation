<template>
  <form class="ion-padding" @submit.prevent="submitForm">
    <ion-list>
      <ion-item>
        <ion-label position="floating">Title</ion-label>
        <ion-input type="text" required v-model="memory.title"></ion-input>
      </ion-item>
      <ion-item>
        <ion-label position="floating">Image URL</ion-label>
        <ion-input type="url" required v-model="memory.image"></ion-input>
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
} from "@ionic/vue";
export default defineComponent({
  emits: ["savememory"],
  components: {
    IonList,
    IonItem,
    IonLabel,
    IonInput,
    IonTextarea,
    IonButton,
  },
  data() {
    return {
      memory: {
        id: new Date().toISOString(),
        title: "",
        image: "",
        description: "",
      },
    };
  },
  methods: {
    submitForm() {
      this.$emit("savememory", this.memory);
      this.$router.replace("/memories");
    },
  },
});
</script>
