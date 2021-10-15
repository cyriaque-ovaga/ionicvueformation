<template>
  <ion-item>
    <ion-thumbnail slot="start">
      <ion-img :src="memory.image" :alt="memory.title"></ion-img>
    </ion-thumbnail>
    <ion-label>
      {{ memory.title }}
    </ion-label>
  </ion-item>
</template>

<script lang="ts">
import { IonItem, IonImg, IonThumbnail, IonLabel } from "@ionic/vue";
import { defineComponent } from "vue";
import { useRouter } from "vue-router";
export default defineComponent({
  props: ["memory"],
  components: {
    IonItem,
    IonImg,
    IonThumbnail,
    IonLabel,
  },
  setup() {
    const router = useRouter();
    return { router };
  },
  data() {
    return {};
  },
  computed: {},
});
</script>
