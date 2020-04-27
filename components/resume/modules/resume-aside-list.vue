<template>
  <section class="mod-aside-list">
    <h5
      v-if="title"
      v-html="title"
      class="type--bold-sc">
    </h5>
    <span
      v-if="subTitle"
      v-html="subTitle"
      class="type--bold-sc">
    </span>
    <ul
      v-if="items.length"
    >
      <li
          v-for="(item, index) in items"
          :key="index"
      >
        <span v-html="item"></span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'resume-aside-list',
  props: {
    title: {
      type: String
    },
    subTitle: {
      type: String
    },
    items: {
      type: Array,
      default: function () {
        return { items: [] }
      }
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

</style>


