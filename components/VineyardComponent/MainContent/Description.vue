<template>
  <div id="description__container">
    <div class="description__content">
      <p>{{ selected.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selected: {
      type: Object,
      default: null,
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#description__container {
  max-width: 777px;
  margin-left: 175px;
  .description__content {
    margin-top: 160px;
  }
}

@media screen and (max-width: $mWidthBig) {
  #description__container {
    max-width: 70%;
    margin-left: 50px;
    padding-right: 50px;
  }
}

@media screen and (max-width: $mWidthMedium) {
  #description__container {
    max-width: 60%;
  }
}

@media screen and (max-width: $mWidthMobile) {
  #description__container {
    max-width: 100%;
    margin-left: 20px;
    padding-right: 20px;
  }
  .description__content {
    margin-top: 40px !important;
  }
}
</style>
