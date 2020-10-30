<template>
  <div class="test">
    <vue-tiny-slider
      id="LandingLocations__container"
      v-bind="tinySliderOptions"
    >
      <div
        v-for="vineyard in vineyards"
        :id="vineyard.id"
        :key="vineyard.id"
        :class="{ triangel: vineyard.isActive }"
        @click="setActive"
      >
        <img :src="getImgUrl(vineyard.logo)" class="tns-lazy-img" />
        <h3>{{ vineyard.name }}</h3>
      </div>
    </vue-tiny-slider>
  </div>
</template>

<script>
export default {
  props: {
    vineyards: {
      type: Array,
      default: null,
    },
  },
  data() {
    return {
      tinySliderOptions: {
        mouseDrag: true,
        loop: false,
        items: 1,
        swipeAngle: false,
        slideBy: 'page',
        freezable: false,
        center: true,
        navContainer: false,
        responsive: {
          350: {
            items: 2,
          },
          700: {
            items: 5,
          },
          900: {
            items: 5,
            disable: true,
          },
        },
      },
    }
  },
  methods: {
    setActive(event) {
      const id = event.currentTarget.id
      for (const [key] in this.vineyards) {
        if (this.vineyards[key].id === id) {
          this.vineyards[key].isActive = true
          this.$emit('clicked', key)
        } else {
          this.vineyards[key].isActive = false
        }
      }
    },
    getImgUrl(pic) {
      return require('~/assets/images/' + pic)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/styles/variables.scss';
#LandingLocations__container {
  display: flex;
  position: absolute;
  text-align: center;
  gap: 95px;
  bottom: 0;
  h3 {
    font-size: 30px;
    line-height: 33px;
    font-family: CourierPrimeBold;
    color: $landingTextColor;
    padding-top: 8px;
  }
  img {
    height: 87px;
    width: 100%;
    max-width: 130px;
    filter: grayscale(100%) brightness(200%);
  }
  div {
    padding-bottom: 85px;
    position: relative;
    z-index: 999;
    cursor: pointer;
    &:hover {
      transform: scale(1.03);
    }
  }
  .triangel::before,
  div:hover::before {
    content: '';
    position: absolute;
    bottom: 0;
    width: 0;
    height: 0;
    left: 50%;
    margin-left: -35px;
    border-style: solid;
    border-width: 0 35px 20px 35px;
    border-color: transparent transparent #fff transparent;
    h3 {
      margin-top: 10px;
    }
  }
  .triangel {
    &:focus,
    &:active {
      outline: none;
    }
  }
}

@media screen and (max-width: $mWidthMedium) {
  #LandingLocations__container {
    text-align: center;
    gap: 95px;
    img {
      height: 40px;
      max-width: 60px;
      margin: 0 auto;
    }
    div {
      padding-bottom: 50px;
    }
  }
}
</style>
