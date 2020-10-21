<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.value }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    items: Array,
  },
};
</script>