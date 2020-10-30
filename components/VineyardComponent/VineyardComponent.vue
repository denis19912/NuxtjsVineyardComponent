<template>
  <div>
    <Landing :vineyards="vineyards" @clicked="changeVineyard" />
    <MainContent :selected="selected" />
  </div>
</template>

<script>
import Landing from '~/components/VineyardComponent/Landing/Landing.vue'
import MainContent from '~/components/VineyardComponent/MainContent/MainContent.vue'
export default {
  components: {
    Landing,
    MainContent,
  },
  props: {
    vineyards: {
      type: Array,
      default: null,
    },
    selected: {
      type: Object,
      default: null,
    },
  },
  methods: {
    changeVineyard(value) {
      this.$emit('clicked', value)
    },
  },
}
</script>
