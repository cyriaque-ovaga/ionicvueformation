<template>
  <base-layout page-title="All memories">
    <MemoryList :memories="memories"></MemoryList>
  </base-layout>
</template>

<script lang="ts">
import MemoryList from "../components/memories/MemoriesList.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: {
    MemoryList,
  },

  computed: {
    memories() {
      return this.$store.getters.memories;
    },
  },
});
</script>
