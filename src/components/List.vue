<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.value }} 
        <ActionButton :itemID="item.id" :action="removeItem" actionName="remove"/>
        <ActionButton :itemID="item.id" :action="duplicateItem" actionName="duplicate"/>
      </li>
    </ul>
  </div>
</template>

<script>
import ActionButton from "./ActionButton"
export default {
  name: "List",
  props: {
    items: Array,
  },
  methods: {
    removeItem(itemID) {
      this.$emit("remove", itemID)
    },
    duplicateItem(itemID) {
      this.$emit("duplicate", itemID)
    }
  },
  components: {
    ActionButton
  }
};
</script>

<style>
  
  ul {
    display:flex;
    flex-direction: column;
    align-items:center;
  }

  li {
    list-style-type: none;
    display: inline-flex;
  }

</style>
