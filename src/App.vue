

<template>
  <CHeader />
  <router-view/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CHeader from '@/components/CHeader.vue';

export default defineComponent({
  name: 'App',
  components: {
    CHeader,
  },
});
</script>

<style>
*{
  font-family: 'Nunito Sans', sans-serif;
}
body{
  margin:0px
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
