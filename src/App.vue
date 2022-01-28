<template>
  <div class="container mt-4 p-2">
    <h3 class="text-center">ToDo App</h3>
    <hr class="my-2" />
    <AddSection :addNewTodo="addNewTodo" @add-todo="addNewTodo" />
    <ListSection />
  </div>
</template>

<script>
import AddSection from "@/components/AddSection";
import ListSection from "@/components/ListSection";

export default {
  components: {
    AddSection,
    ListSection,
  },
  data() {
    return {
      provideData: {
        todoList: [
          { id: 1, text: "Learn Vue" },
          { id: 2, text: "Learn Angular" },
          { id: 3, text: "Html and Css practice" },
          { id: 4, text: "Read Software Article" },
          { id: 5, text: "Will go Sport" },
          { id: 6, text: "Watch Movie" },
        ],
      },
    };
  },
  provide() {
    return {
      provideData: this.provideData,
      deleteItem: this.deleteItem,
    };
  },
  methods: {
    testEvent(data) {
      alert(data);
    },
    deleteItem(todoItem) {
      this.provideData.todoList = this.provideData.todoList.filter(
        (t) => t !== todoItem
      );
    },
    addNewTodo(todo) {
      this.provideData.todoList.push({
        id: new Date().getTime(),
        text: todo,
      });
    },
  },
};
</script>