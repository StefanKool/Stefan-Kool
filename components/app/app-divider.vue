<template>
  <div class="comp-app-divider">
  </div>
</template>

<script>
export default {
  name: 'app-divider'
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.comp-app-divider {
  clip-path: polygon(0 100%, 0 0, 100% 0);
  height: 160px;
  background-color: $color-brand-primary;
  &.app-divider--reverse {
    clip-path: polygon(0 100%, 100% 100%, 100% 0);
  }
  &.app-divider--alternate {
    background-color: $color-grey-100;
  }
}
</style>
