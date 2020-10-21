<template>
  <div id="app">
    <HelloWorld msg="Hello" />
    <List :items="items" />
    <ItemCreator @create="addItem" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import List from "./components/List";
import ItemCreator from "./components/ItemCreator";
import ItemRemover from "./components/ItemRemover";

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
  },
  components: {
    HelloWorld,
    List,
    ItemCreator,
    ItemRemover,
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
