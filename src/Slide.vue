<template>
  <div class="VueCarousel-slide">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "slide",
    data() {
      return {
        width: null,
      }
    }
  }
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
