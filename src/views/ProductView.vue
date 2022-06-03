<script lang="ts">
    import { Product } from "@/service/Product.model";
import { ProductService } from "@/service/ProductService";
    import { defineComponent } from "vue";
    declare interface BaseComponentData {
        product:Product|null
    }
    
    export default defineComponent({
        name:"ProductView",
        data():BaseComponentData{
                return {
                    product:null
                }
            },
        beforeMount(){
            const idParam = String(this.$route.params.id);
            ProductService.getById(Number.parseInt(idParam))
                .then((product)=>{
                  console.log(product)
                    this.product = product;
                })
        }
    })
</script>

<template>
    <div class="product-container">
        <div class="container-row">
            <img class="image" v-bind:src="product?.imagen"/>
            <div>
                <p>{{product?.descripcion}}</p>
            </div>
        </div>
        <div class="container-row">
            <div>
                <span class="sub-title">{{product?.cantidadVendida}} vendidios</span>
                <h1 class="title">{{product?.instrumento}}</h1>
            </div>
            <div>
                <p><span>Marca</span>: {{product?.marca}}</p>
                <p><span>Modelo</span>: {{product?.modelo}}</p>
            </div>
        </div>
    </div>
</template>

<style>
    .product-container{
        display: flex;
        margin: 8px;
    }
    .product-container .container-row{
        flex: 1 1 0%;
    }
    .sub-title{
        color: rgb(154, 154, 154);
        padding: 0px;
    }
    .product-container .container-row .image{
        width: 100%;
        height: 300px;
        object-fit: cover;
        border-radius: 4px;
    }

</style>