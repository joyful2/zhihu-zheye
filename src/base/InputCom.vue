 
<template>
  <div>
    <input
      type="text"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <button @click="$emit('handle-add')">添加</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "InputCom",
  props: {
    modelValue: {
      type: String,
      required: true,
    },
  },

  emits: ["handle-add"],
});
</script>
 