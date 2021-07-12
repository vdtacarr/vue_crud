<template>
  <div id="app">
    <ProductAppend @add:product="addProduct"/>

    <ProductList @delete:product="deleteProduct"  :products="products"/>
  </div>
</template>

<script>
import ProductAppend from'./components/ProductAppend.vue'

import ProductList from'./components/ProductList.vue'


export default {
  name: 'App',
  components: {
    ProductList,ProductAppend
  },
  data(){
return{
  products : [
{id:1,categoryId:1,productName:'Laptop',quantityPerUnit:'Acer Laptop',unitPrice:5000,unitsInStock:1},
{id:2,categoryId:2,productName:'Mouse',quantityPerUnit:'Acer Mouse',unitPrice:50,unitsInStock:3},
{id:3,categoryId:3,productName:'Keyboard',quantityPerUnit:'Acer Keyboard',unitPrice:500,unitsInStock:20},

  ]
}
    },
    methods:{
      deleteProduct(product){
        this.products = this.products.filter(
          productToFilter => productToFilter.id!==product.id
        )

        
        },
        addProduct(product){
const newProduct = {...product}
this.products = [...this.products,newProduct]
        }

}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
 
  color: #2c3e50;
  margin-top: 60px;
}
</style>
