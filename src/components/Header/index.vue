<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "MyHeader"
}
</script>
<style lang="scss" scoped>
 div{
   text-align: center;
   background-color: red;
   font-size: 0.3rem;
   color: white;
 }
</style>