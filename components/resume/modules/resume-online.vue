<template>
  <section class="mod-online-spaces">
    <h5 v-if="title" v-html="title" class="type--bold-sc"></h5>
    <span v-if="subTitle" v-html="subTitle" class="type--bold-sc"></span>
    <ul v-if="items.length">
      <li v-for="(item, index) in items" :key="index">
        <span
          class="resume__icon-panel"
          :style="{ backgroundColor: item.backgroundColor }"
          ><app-icon :iconId="item.icon"
        /></span>
        <nobr
          ><a :href="item.href" :title="item.hrefTitle">{{
            item.title
          }}</a></nobr
        >
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'resume-online',
  props: {
    title: {
      type: String
    },
    subTitle: {
      type: String
    },
    items: {
      type: Array,
      default: function() {
        return { items: [] }
      }
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.mod-online-spaces {
  ul {
    list-style: none;
    padding: 0;
  }
  .resume__icon-panel {
    display: inline-block;
  }
}

.resume__icon-panel {
  display: inline-block;
  width: 2rem;
  height: 2rem;
  border-radius: 4px;
  line-height: 2rem;
  text-align: center;
  margin-right: 0.5rem;
  background-color: var(--color-grey-300);
  background-size: cover;
  background-position: center;
  svg {
    fill: var(--color-grey-100);
  }
}
</style>
