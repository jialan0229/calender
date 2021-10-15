<template>
  <div class="container">
    Year Page
  </div>
</template>

<script>

import getData from '@/services';
import { onMounted,computed } from 'vue';
import { useRouter } from 'vue-router';
import { useStore } from 'vuex'

import { getNoDate } from '@/libs/utils.js'

export default {
  name: 'MonthPage',
  setup() {
    const router = useRouter(),
          store = useStore(),
          state = store.state;

    onMounted(() => {
      getData(store,'year', getNoDate('year'));
    });
    
    return {
      yearData: computed(() => state.yearData)
    }
  }
}
</script>
<style lang="scss" scoped>

</style>