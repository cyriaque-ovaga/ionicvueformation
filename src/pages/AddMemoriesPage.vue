<template>
  <base-layout pageTitle="Add a Memory" pageDefaultBackLink="/memories">
    <CreateMemoryForm @savememory="savememory"> </CreateMemoryForm>
  </base-layout>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CreateMemoryForm from "@/components/memories/CreateMemoryForm.vue";
export default defineComponent({
  components: {
    CreateMemoryForm,
  },
  methods: {
    savememory(memoryData) {
      this.$store.dispatch("addMemory", memoryData);
    },
  },
});
</script>
