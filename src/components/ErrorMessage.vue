<template>
  <div class="message-err">
    <span>{{this.$props.errmsg}}</span>
  </div>
</template>

<script>
export default {
  name: "ErrorMessage",
  props:{
    errmsg:{
      type:String,
      require:true
    }
  }
}
</script>

<style scoped>
  .message-err{
    background: #ff1654;
    color: #fff;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 6px 0px;
  }
</style>