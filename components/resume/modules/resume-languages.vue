<template>
  <section class="mod-languages">
    <h5 v-if="title" v-html="title" class="type--bold-sc"></h5>
    <span v-if="subTitle" v-html="subTitle" class="type--bold-sc"></span>
     <ul v-if="items.length">
      <li v-for="(item, index) in items" :key="index">
        <app-icon class="resume__icon-panel app-icon--flag" :iconId="item.icon" />
        <div class="resume__progress-bar">
          <div
            class="resume__progress-bar-indication"
            :style="{ width: item.width }"
          ></div>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'resume-languages',
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
@import "~assets/scss/utilities.scss";

.mod-languages {
  ul {
    list-style: none;
    padding: 0;
    li {
      display: flex;
    }
  }
}

.app-icon--flag {
  display: block;
}

.resume__progress-bar {
  height: 0.6rem;
  margin: 0.7rem 0;
  background-color: #f3f3f3;
  border-radius: 4px;
  overflow: hidden;
  flex-grow: 1;
}

.resume__progress-bar-indication {
  background-color: #192d40;
  height: 0.6rem;
  width: 0%;
  border-radius: 4px;
}
</style>


