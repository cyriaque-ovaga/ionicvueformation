<template>
  <base-layout page-title="All memories">
    <template v-slot:actions-end>
      <ion-button @click="() => router.push('/memories/add')">
        <ion-icon color="light" slot="icon-only" :icon="add"></ion-icon>
      </ion-button>
    </template>
    <MemoryList :memories="memories"></MemoryList>
  </base-layout>
</template>

<script lang="ts">
import MemoryList from "../components/memories/MemoriesList.vue";
import { defineComponent } from "vue";
import { IonButton, IonIcon } from "@ionic/vue";
import { add } from "ionicons/icons";
import { useRouter } from "vue-router";

export default defineComponent({
  components: {
    MemoryList,
    IonButton,
    IonIcon,
  },
  data() {
    return {
      add,
    };
  },
  computed: {
    memories() {
      return this.$store.getters.memories;
    },
  },
  setup() {
    const router = useRouter();
    return { router };
  },
});
</script>
