<template>
  <div id="app">
    <HelloWorld msg="Hello" />
    <List :items="items" @remove="removeItem" @duplicate="duplicateItem" />
    <ItemCreator @create="addItem" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import List from "./components/List";
import ItemCreator from "./components/ItemCreator";

export default {
  name: "App",
  data() {
    return {
      items: [
        {
          value: "item 1",
          id: 1,
        },
      ],
    };
  },
  methods: {
    addItem(value) {
      this.items.push(value);
    },

    removeItem(itemID) {
      this.items = this.items.filter(item => item.id != itemID)
    },

    duplicateItem(itemID) {
      const value = this.items.find(item => item.id == itemID).value
      const duplicateItem = {
        value,
        id: Date.now()
      }
      this.items.push(duplicateItem);
    },
  },
  components: {
    HelloWorld,
    List,
    ItemCreator,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
