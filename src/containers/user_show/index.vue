
<template>
  <LayoutView :model="model"/>
</template>

<!-- // // // //  -->

<script>
import LayoutView from './components/layout.vue'
import store from '@/store'

export default {
  props: ['id'],
  components: {
    LayoutView
  },
  metaInfo: {
    title: 'User Show' // title is now "RCOS - User Show..."
  },
  created () {
    this.fetch()
  },
  methods: {
    fetch () {
      return store.dispatch('user/fetchModel', this.id)
    }
  },
  computed: {
    model () {
      return store.getters['user/current']
    }
  }
}
</script>


