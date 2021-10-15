<template>
  <div class="list-item">
    <div class="block title">{{ title }}</div>
    <div class="block content">{{ content }}</div>
  </div>
</template>

<script>
export default {
  name:'ListItem',
  props: {
    title:String,
    content: String
  }
}
</script>
<style lang="scss" scoped>
  .list-item{
    width: .5rem;
  }
</style>