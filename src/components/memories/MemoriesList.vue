<template>
  <ion-list>
    <MemoriesListItem
      v-for="item in memories"
      :key="item.id"
      :memory="item"
      @click="() => router.push('/memories/' + item.id)"
    ></MemoriesListItem>
  </ion-list>
</template>

<script lang="ts">
import { IonList } from "@ionic/vue";
import { defineComponent } from "vue";
import { useRouter } from "vue-router";
import MemoriesListItem from "./MemoriesListItem.vue";
export default defineComponent({
  props: ["memories"],
  components: {
    IonList,
    MemoriesListItem,
  },
  setup() {
    const router = useRouter();
    return { router };
  },
});
</script>
