<template>
  <section class="resume-section">
    <h2 class="h3 type--bold-sc" v-if="title">
      {{ title }}
    </h2>
    <ul class="resume__list">
      <resume-item
        v-for="(item, index) in resumeItems"
        :key="index"
        :title="item.title"
        :subTitle="item.subTitle"
        :description="item.description"
        :startYear="item.startYear"
        :endYear="item.endYear"
        :portfolioItems="item.portfolio"
      />
    </ul>
  </section>
</template>

<script>
import ResumeItem from '@/components/resume/modules/resume-item.vue'

export default {
  name: 'resume-section',
  components: {
    ResumeItem
  },
  props: {
    title: {
      type: String
    },
    resumeItems: {
      type: Array
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.resume__list {
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
