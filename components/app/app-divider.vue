<template>
  <hr class="comp-app-divider" />
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
  height: 0;
  padding: 0;
  padding-bottom: 5%;
  margin: 0;
  border-width: 0;
  margin-bottom: -1px;
  background-color: $color-brand-primary;
  &.app-divider--reverse {
    clip-path: polygon(0 100%, 100% 100%, 100% 0);
  }
  &.app-divider--alternate {
    background-color: $color-grey-100;
  }
}
</style>
