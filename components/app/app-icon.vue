<template>
  <svg class="app-icon">
    <use v-bind="{ 'xlink:href': '#icon-' + iconId }"></use>
  </svg>
</template>

<script>
export default {
  name: 'app-icon',
  props: {
    iconId: {
      type: String
    }
  }
}
</script>

<style>
.app-icon {
  height: 1rem;
  width: 1rem;
  display: inline-block;
  font-size: inherit;
  overflow: visible;
  vertical-align: -0.12rem;
}
.app-icon--flag {
  color: unset;
  fill: unset;
  overflow: hidden;
}
</style>
