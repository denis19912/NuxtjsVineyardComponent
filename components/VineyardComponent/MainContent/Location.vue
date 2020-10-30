<template>
  <div id="location">
    <img :src="getImgUrl(selected.logo)" />
    <h2>{{ selected.name }}</h2>
    <p>{{ selected.subText }}</p>
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
  methods: {
    getImgUrl(pic) {
      return require('~/assets/images/' + pic)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#location {
  padding-left: 70px;
  padding-top: 90px;
  max-width: 260px;
  h2 {
    font-family: CourierPrimeBold, sans-serif;
    font-size: 42px;
    line-height: 47px;
  }
  img {
    padding-left: 15px;
    height: 60px;
    margin-bottom: 25px;
    max-width: 160px;
  }
  p {
    width: 260px;
    max-width: 260px;
    font-family: CourierPrimeBold, sans-serif;
    font-size: 22px;
    letter-spacing: -1px;
    line-height: 25px;
    color: $locationPromoColor;
  }
}

@media screen and (max-width: $mWidthMedium) {
  #location {
    padding-left: 20px;
    max-width: 30%;
    h2 {
      font-size: 30px;
      line-height: 35px;
    }
    p {
      width: 100%;
    }
  }
}

@media screen and (max-width: $mWidthMobile) {
  #location {
    max-width: 100%;
    padding-top: 40px;
    text-align: center;
    h2 {
      padding-bottom: 20px;
    }
    p {
      width: 100%;
    }
  }
}
</style>
