<template>
  <div class="card-wrapper">
    <div class="card">
      <div class="header">
        <span class="weekday">{{ data.weekday }}</span>
      </div>
      <h1 class="text lunar">{{ data.lunar }}</h1>
      <h1 class="text date">{{ data.date }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    data: Object
  }
}
</script>
<style scoped>

</style>