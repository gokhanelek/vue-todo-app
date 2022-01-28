<template>
  <li
    class="
      d-flex
      justify-content-between
      align-items-center
      list-group-item list-group-item-secondary
      mb-2
    "
  >
    <span class="item-text">{{ item.text }}</span>
    <button @click="deleteItem(item)" type="button" class="btn btn-danger">
      Sil
    </button>
  </li>
</template>
<script>
export default {
  props: ["item"],
  inject: ["deleteItem"],
};
</script>
