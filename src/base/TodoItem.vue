 
<template>
  <li>{{ item }} <button @click="handleDel(i)">-</button></li>
</template>

<script lang="ts">
import { defineComponent, inject } from "vue";

export default defineComponent({
  name: "TodoItem",

  props: {
    item: {
      type: String,
      required: true,
    },

    i: {
      type: Number,
      required: true,
    },
  },

  setup() {
    const handleDel = inject("handleDel");
    return { handleDel };
  },
});
</script>

 