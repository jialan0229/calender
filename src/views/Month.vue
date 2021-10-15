<template>
  <div class="container">
    Month Page
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
  components: {
       
  },
  setup() {
     const router = useRouter(),
           store = useStore(),
           state = store.state;

    onMounted(() => {
      getData(store,'month', getNoDate('month'));
    });
    
    return {
      monthData: computed(() => state.monthData)
    }
  }
}
</script>
<style lang="scss" scoped>

</style>