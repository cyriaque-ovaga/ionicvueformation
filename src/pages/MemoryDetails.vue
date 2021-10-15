<template>
  <base-layout
    :page-title="loadedmemory ? loadedmemory.title : 'Loading'"
    page-Default-Back-Link="/memories"
  >
    <MemoriesOverView
      v-if="loadedmemory"
      :memory="loadedmemory"
    ></MemoriesOverView>

    <h2 v-else>Il existe pas</h2>
  </base-layout>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MemoriesOverView from "../components/memories/MemoriesOverView.vue";
export default defineComponent({
  components: {
    MemoriesOverView,
  },
  data() {
    return {
      memoryId: this.$route.params.id,
    };
  },
  computed: {
    loadedmemory() {
      return this.$store.getters.memory(this.memoryId);
    },
  },
});
</script>
