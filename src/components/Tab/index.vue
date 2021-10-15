<template>
  <div class="tab">
    <div 
      class="tab-item"
      v-for="(item, index) of tabData"
      :key="index"
    >
      <tab-icon
        :iconText='item.iconText'
        :path='item.path'
      >{{ item.tabText }}</tab-icon>
    </div>
  </div>
</template>

<script>
import TabIcon from './icon.vue'

import tabData from '@/data/tab'

import { reactive } from 'vue'

export default {
  name: 'Tab',
  components: {
    TabIcon
  },
  setup() {
    const store = reactive({
      tabData
    })

    return {
      ...store
    }
  }
}
</script>
<style lang="scss" scoped>
  .tab{
    display: flex;
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;

    .tab-item{
      display: flex;
      justify-content:center;
      // align-items:flex-end;
      width: 50%;
      height: 100%;
    }
  }
</style>