<template>
  <base-layout page-title="The Details" page-Default-Back-Link="/memories">
    <h2>dETAILS {{ key }}</h2></base-layout
  >
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  data() {
    return {
      key: "value",
    };
  },
});
</script>
