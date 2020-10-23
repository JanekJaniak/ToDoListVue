<template>
  <div>
    <input :value="value" @input="handleInput" />
    <button @click="handleButton">Add Item</button>
  </div>
</template>

<script>
export default {
  name: "ItemCreator",
  data() {
    return {
      value: "",
    };
  },
  methods: {
    handleInput(event) {
      this.value = event.target.value;
    },
    handleButton() {
      const item = {
        value: this.value,
        id: Date.now(),
      };
      if(this.value== "") return;
      this.$emit("create", item);
      this.value= "";
    },
  },
};
</script>