<template>
  <div id="nav">
    <my-header>{{ headerTitle }}</my-header>
    <SearchInput
      :placeholder="placeholder"
      :maxlength="maxlength"
    />
    <Tab/>
    <router-view/>
  </div>
</template>

<script>
import MyHeader from '@/components/Header'
import SearchInput from '@/components/SearchInput'
import Tab from '@/components/Tab'

import { computed, watch } from 'vue'
import { useStore } from 'vuex'
import { useRouter } from 'vue-router'

export default {
  name: "App",
  components: {
    MyHeader,
    SearchInput,
    Tab
  },
  setup() {
    const store = useStore(),
          state = store.state,
          router = useRouter();

    router.push("/")

    watch(() => {
      return router.currentRoute.value.name
    }, (v) => {
      store.commit('setHeaderTitle',v)
      store.commit('setPlaceholder',v)
      store.commit('setMaxlength',v)
    })

    return computed(() => state).value
  }
}
</script>

<style lang="scss">
</style>
