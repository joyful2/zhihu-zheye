 
<template>
  <div>
    <InputCom v-model="input" @handle-add="handleAdd" />
    <TodoList :list="list" />
  </div>
</template>

<script lang="ts">
import { defineComponent, provide, reactive, ref, readonly } from "vue";
import TodoList from "../base/TodoList.vue";
import InputCom from "../base/InputCom.vue";

export default defineComponent({
  name: "TodoListCom",
  data() {
    return {
      list: ["--a", "B", "c"],
      input: "d",
    };
  },
  components: {
    TodoList,
    InputCom,
  },

  methods: {
    handleAdd() {
      this.list.push(this.input);
      this.input = "";
    },

    handleDel(index: number) {
      this.list.splice(index, 1);
    },
  },

  created() {
    const handleDel = this.handleDel;
    provide("handleDel", handleDel);
  },
});
</script>
 
