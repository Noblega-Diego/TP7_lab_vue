<template>
  <div class="about">
    <h1>List of Products</h1>
    <ErrorMessage v-if="err !== ''" :errmsg="err"></ErrorMessage>
    <div v-if="err === '' && products.length === 0" style="width: 100%; display: flex; justify-content: center">
      <LoadingA ></LoadingA>
    </div>
    <CardProduct v-for="product of products" :product='product' v-bind:key="product.id"></CardProduct>
  </div>
</template>

<script lang="ts">

  import { defineComponent} from "vue";
  import CardProduct from "@/components/CardProduct.vue";
  import { ProductService } from "@/service/ProductService";
  import {Product} from "@/service/Product.model";
  import ErrorMessage from "@/components/ErrorMessage.vue";
  import LoadingA from "@/components/LoadingA.vue";
  export default defineComponent({
    name: 'ProductsView',
    data(){
      return{
        products: Array<Product>(),
        err: ""
      };
    },
    components: {
      LoadingA,
      ErrorMessage,
      CardProduct
    },
    beforeMount(){
      ProductService.getAll().then((ps)=>{
        console.log(ps)
        this.products = ps;
      }).catch(e=>{this.err=":/ No es posible establecer conexión con nuestros servidores"})
    }
    
  });

</script>
