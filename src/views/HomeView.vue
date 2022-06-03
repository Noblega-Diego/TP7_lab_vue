<template>
  <div class="home">
    <div class="banner">
      <p>La mejor Pagina web de ventas</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeView',
  components: {
  }
});
</script>

<style>
  .home{
    width: 100%;
    min-height: 100vh;
    display: flex;
    justify-content: center;
  }
 
  .banner{
    margin-top: 12px;
    width: 90%;
    height: 100px;
    background: #42b983;
    color: aliceblue;
    border-radius: 6px;
  }

</style>