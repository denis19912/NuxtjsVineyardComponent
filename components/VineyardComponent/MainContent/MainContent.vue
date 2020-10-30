<template>
  <div id="main-content">
    <Location :selected="selected" />
    <Description :selected="selected" />
  </div>
</template>

<script>
import Location from '~/components/VineyardComponent/MainContent/Location.vue'
import Description from '~/components/VineyardComponent/MainContent/Description.vue'

export default {
  components: {
    Location,
    Description,
  },
  props: {
    selected: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      content: 1,
    }
  },
}
</script>

<style scoped lang="scss">
@import '~assets/styles/variables.scss';
#main-content {
  display: flex;
  align-items: center;
  margin-bottom: 10vh;
  flex-wrap: wrap;
}
@media screen and (max-width: $mWidthMobile) {
  #main-content {
    justify-content: center;
  }
}
</style>
