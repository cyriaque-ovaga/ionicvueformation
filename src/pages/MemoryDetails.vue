<template>
  <base-layout
    :page-title="loadedmemory ? loadedmemory.title : 'Loading'"
    page-Default-Back-Link="/memories"
  >
    <h2 v-if="loadedmemory">{{ loadedmemory.description }}</h2>
    <h2 v-else>Il existe pas</h2>
  </base-layout>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
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
