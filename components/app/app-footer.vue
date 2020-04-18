<template>
  <footer class="comp comp-app-footer">
    <div class="container container--flex container--max-10-col">
      <nuxt-link to="/">
        footer nav Home
      </nuxt-link>
      <nuxt-link to="/design-system">
        footer nav Design system
      </nuxt-link>
    </div>
  </footer>
</template>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.comp-app-footer {
  padding: 60px 0;
  min-height: 300px;
  background: $color-grey-900;
  a {
    color: $color-grey-0;
  }
}
</style>
