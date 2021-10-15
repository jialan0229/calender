<template>
  <div class="search-wrap">
    <input type="text"
      :placeholder="placeholder"
      :maxlength="maxlength"
      :value="inputValue"
      @input="searchData($event)"
    >
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'SearchInput',
  props: {
    placeholder: String,
    maxlength: Number
  },
  setup() {
    const inputValue = ref('')
    const searchData = (e) => {

    }

    return {
      inputValue,
      searchData
    }
  }
}
</script>
<style scoped>

</style>