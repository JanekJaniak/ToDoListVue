<template>
    <div>
        <button @click="handleButton">{{actionName}}</button>
    </div>   
</template>
<script>
export default {
    name: "ItemRemover",
    props: {
        itemID: Number,
        action: Function,
        actionName: String,
    },
    methods:{
        handleButton() {
            this.action(this.itemID)
        },
    }
};
</script>
