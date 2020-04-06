<template>
  <nav class="comp-app-nav">
    <nuxt-link to="/">
      <h1 class="nav-logo">
        <span class="type--regular-sc type--uppercase">Stefan</span><span class="type--thin-cpr-sc type--uppercase">Kool</span>
      </h1>
    </nuxt-link>
    <nuxt-link to="/">
      Home
    </nuxt-link>
  </nav>
</template>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.comp-app-nav {
  padding: 16px;
  background: $color-brand-primary;
  display: flex;
  justify-content: space-between;
  a {
    color: $color-grey-0;
  }
}

.nav-logo {
  font-size: 1rem;
  margin: 0;
}
</style>

