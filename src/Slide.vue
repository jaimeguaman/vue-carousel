<template>
  <div class="VueCarousel-slide" v-bind:style="`
    -ms-flex-preferred-size: ${slideWidth > 1 ? slideWidth + 'px' : 'inherit'};
    flex-basis: ${slideWidth > 1 ? slideWidth + 'px' : 'inherit'};
    ${slideWidth > 1 ? 'min-width:' + slideWidth + 'px' : ''};
  `">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "slide",
  inject: ["carousel"],
  computed: {
    slideWidth() {
      return this.carousel.slideWidth;
    }
  },
  mounted() {
    if (!this.$isServer) {
      this.$el.addEventListener("dragstart", e => e.preventDefault());
    }
  }
};
</script>

<style>
.VueCarousel-slide {
  -ms-flex-preferred-size: inherit;
  flex-basis: inherit;
  -webkit-box-flex: 0;
  -ms-flex-positive: 0;
  flex-grow: 0;
  -ms-flex-negative: 0;
  flex-shrink: 0;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
</style>
