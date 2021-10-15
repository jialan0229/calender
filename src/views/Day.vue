<template>
  <div class="container">
    <day-card :data="dayData" />
    <day-list :data="dayData"/>
  </div>
</template>

<script>

import getData from '@/services/index.js';
import { computed, onMounted } from 'vue';
// import { useRouter } from 'vue-router';
import { useStore } from 'vuex';

import DayCard from '@/components/DayPage/Card';
import DayList from '@/components/DayPage/List'

import { getNoDate } from '@/libs/utils.js'

export default {
  name: 'DayPage',
  components:{
    DayCard,
    DayList
  },
  setup() {
    const store = useStore(),
          state = store.state;

    onMounted(() => {
      getData(store,'day', getNoDate('day'));
    });
    
    return {
      dayData: computed(() => state.dayData)
    }
  }
}
</script>
<style lang="scss" scoped>

</style>