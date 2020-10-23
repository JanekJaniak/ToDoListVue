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
        removeItem(event) {  
            console.log(event);
            this.$emit("remove", );
        }
    }
};

list

</script>