<template>
    <div>
        <button @click="handleButton">Remove</button>
    </div>   
</template>

<script>
export default {
    name: "ItemRemover",
    handleButton(){
    },
    methods:{
        deleteObject(id) {
            this.$delete(this.items, id);
        }
    }
};
</script>