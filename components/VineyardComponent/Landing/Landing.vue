<template>
  <div id="landing">
    <LandingLocations :vineyards="vineyards" @clicked="changeVineyard" />
  </div>
</template>

<script>
import LandingLocations from '~/components/VineyardComponent/Landing/LandingLocations.vue'
export default {
  components: {
    LandingLocations,
  },
  props: {
    vineyards: {
      type: Array,
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

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#landing {
  background: url('~assets/images/landing.png');
  background-size: cover;
  background-position: right;
  background-repeat: no-repeat;
  width: 100%;
  height: 766px;
  position: relative;
  padding: 0 70px;
  overflow: hidden;
}
@media screen and (max-width: $mWidthMedium) {
  #landing {
    height: 600px;
  }
}
@media screen and (max-width: $mWidthMobile) {
  #landing {
    height: 400px;
  }
}
</style>
