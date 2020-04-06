<template>
  <section class="comp comp-t-shape">
    <div class="container container--max-10-col">
      <h2>T-shape</h2>
      <nuxt-link class="button" to="/resume">
        Go to resume
      </nuxt-link>
    </div>
  </section>
</template>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.comp-t-shape {
  text-align: center;
  background: $color-grey-100;
}
</style>
