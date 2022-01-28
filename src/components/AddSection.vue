<template>
  <input
    class="form-control mb-2 mt-2"
    v-model="todoText"
    @keydown.enter="addNewTodo(todoText)"
    type="text"
    id="todoText"
    placeholder="Enter to-do item... "
  />
</template>

<script>
export default {
  props: {
    addNewTodo: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      todoText: null,
    };
  },
};
</script>