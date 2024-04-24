<template>
  <ElectronicHeader/>
  <div class="button-div">
    <button @click="toggleComponent" v-if="componentVisible" class="load-button">Hide Products</button>
    <button @click="toggleComponent" v-else class="load-button">Load Products</button>
  </div>
   <div v-if="componentVisible"> 
     <ElectronicItemsList :electronicProducts = electronicProducts />
   </div>
</template>

<script>
  import ElectronicHeader from "./components/ElectronicHeader.vue";
  import ElectronicItemsList from "./components/ElectronicItemsList.vue";

  export default{
    name:"App",
    components:{
      ElectronicHeader,
      ElectronicItemsList
    },
    data(){
      return{
        electronicProducts:[],
        componentVisible: false
      }
    },
    methods:{
      async fetchProductDetails(){
        const res = await fetch("https://homeelectronics.onrender.com/api");
        const products = await res.json();
        return products[0].electronicItems;
      },
      toggleComponent() {
        this.componentVisible = !this.componentVisible;
      } 
    },
    async created(){
      this.electronicProducts = await this.fetchProductDetails();
    }
  }
</script>

<style scoped>
  .load-button{
    padding: 1em;
    border: 1px solid #6b9080;
    border-radius: 5px;
    background-color: #6b9080;
    color: white;
    cursor: pointer;
    font-size: 1em;
  }
  .button-div{
    text-align: center;
    margin-bottom: 3em;
  }
</style>