<template>
    <div class="grid">
        <div v-for="item of electronicProducts" :key="item.item_id" >
            <ElectronicItem :item = item />
        </div>
    </div>
</template>

<script>
    import ElectronicItem from "./ElectronicItem.vue";

    export default{
        name:"ElectronicItemsList",
        components:{
            ElectronicItem
        },
        props:{
            electronicProducts:Array,
        }
    }
</script>

<style scoped>
    .grid{
       display:grid;
       grid-template-columns: auto auto auto;
       gap: 1em;
    }
</style>