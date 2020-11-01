<template>
  <div id="app">
    <NavBar />
    <VineyardComponent
      :vineyards="vineyards"
      :selected="selected"
      @clicked="changeVineyard"
    />
    <nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/Menu/NavBar.vue'
import VineyardComponent from '~/components/VineyardComponent/VineyardComponent.vue'
import Vineyards from '~/static/vineyards.json'
export default {
  components: {
    NavBar,
    VineyardComponent,
  },
  data() {
    return {
      vineyards: Vineyards,
      selected: Vineyards[0],
    }
  },
  methods: {
    changeVineyard(value) {
      for (const [key] in this.vineyards) {
        if (key === value) {
          this.vineyards[key].isActive = true
          this.selected = Vineyards[key]
        } else {
          this.vineyards[key].isActive = false
        }
      }
    },
  },
}
</script>

<style scoped>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
#app {
  max-width: 1333px;
  margin: 0 auto;
}
</style>
