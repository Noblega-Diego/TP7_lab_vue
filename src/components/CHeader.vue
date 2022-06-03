<script lang="ts">
    import { defineComponent } from "vue";

    export default defineComponent({
        name: 'CHeader',
        props: {}
    })
</script>

<template>
    <div class="navBar">
        <nav class="nav">
            <router-link to="/">Home</router-link>
            <router-link to="/products">instrumentos</router-link>
        </nav>
    </div>
</template>

<style>
    .navBar{
        width: 100%;
        height: 50px;
        background-color: #f2f5f2;
    }
    .nav {
        position:relative;
        display:flex;
        padding: 0px;
        align-items: center;
        justify-content: space-around;
        height:100%
    }
    .nav a {
        text-decoration: none;
        color: #3D403F;
        font-weight: bold;
    }
</style>