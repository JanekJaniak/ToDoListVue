<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.value }} 
        <button v-on:click="handleRemoveButton(item.id)">remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    items: Array,
  },
  methods: {
    handleRemoveButton(itemID) {
      this.$emit("remove", itemID)
    }
  }
};
</script>
