 
<template>
  <ul>
    <TodoItem
      v-for="(item, index) in list"
      :key="index"
      :i="index"
      :item="item"
    >
    </TodoItem>
  </ul>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TodoItem from "../base/TodoItem.vue";

export default defineComponent({
  name: "TodoList",
  props: {
    list: {
      type: Array,
    },
  },

  components: {
    TodoItem,
  },
});
</script>
 
