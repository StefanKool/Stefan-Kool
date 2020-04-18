<template>
  <hr class="resume__divider" />
</template>

<script>
export default {
  name: 'resume-divider'
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.resume__divider {
  border: none;
  border-top: 1px solid #e7e8e1;
  margin: 16px 0 16px 0;
}

.resume__divider.resume-divider--large {
  margin: 32px 0 16px 0;
}
</style>


