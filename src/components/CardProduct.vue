<script lang="ts">
    import { defineComponent, PropType } from "vue";
    import { Product } from '../service/Product.model';
    export default defineComponent({
        name: 'CardProduct',
        components: {

        },
        props:{
            id:Number,
            product:{
                type: Object as PropType<Product>,
                required:true
            }
        },
        methods:{
          handleImageClick(){
            this.$router.push({path:'/product/'+ this.$props.product.id})
          }
        }
    })
</script>

<template>
    <div class='cardProduct'>
        <img @click.prevent="handleImageClick" v-bind:src="product.imagen"/>
        <div class="card-body">
            <p class="card-title">{{product.instrumento}}</p>
            <div>
                <p class="card-description">{{product.descripcion}}</p>
                <p>$ {{product.precio}}</p>
            </div>
            <button>Agregar</button>
        </div>
    </div>
</template>

<style>
    .cardProduct{
        margin: 8px;
        min-width: 200px;
        max-width: 200px;
        background: rgb(236, 255, 244);
        border-radius: 8px;
    }
    .card-title{
        margin: 2px;
        font-weight: bold;
    }
    .card-description{
        margin: 2px;
        font-size: 0.8rem;
        height: 50px;
    }
    .cardProduct  img{
        width: 100%;
        height: 100px;
        object-fit: cover;
        border-radius: 4px;
    }
    .card-body{
        padding: 8px;
    }
    .card-body button{
        position: relative;
        padding: 4px 8px;
        background-color: rgb(22, 164, 116);
        border: solid 0px;
        border-radius: 50px;
        float: right;
        top: -23px;
        right: -2px;
    }
    
</style>