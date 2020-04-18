<template>
  <li class="resume__item">
    <div class="h4 resume__date" v-if="startYear">
      <span>{{ startYear }} - {{ endYear }}</span>
    </div>
    <h4 v-if="title">
      <span class="type--regular-sc type--uppercase">{{ title }}</span
      ><span
        class="type--thin-cpr-sc type--uppercase type--light"
        v-if="subTitle"
      >
        | {{ subTitle }}</span
      >
    </h4>
    <p v-if="description">
      {{ description }}
    </p>
    <resume-divider v-if="portfolioItems && portfolioItems.length > 0" />
    <ul class="resume__portfolio-list">
      <resume-portfolio-item
        v-for="(item, index) in portfolioItems"
        :key="index"
        :title="item.title"
        :description="item.description"
        :insetPrimary="item.insetPrimary"
        :insetPrimaryWidth="item.insetPrimaryWidth"
        :insetSecondary="item.insetSecondary"
        :insetSecondaryWidth="item.insetSecondaryWidth"
        :backgroundColor="item.backgroundColor"
      />
    </ul>
  </li>
</template>

<script>
import ResumePortfolioItem from '@/components/resume/modules/resume-portfolio-item.vue'
import ResumeDivider from '@/components/resume/modules/resume-divider.vue'

export default {
  name: 'resume-item',
  components: {
    ResumePortfolioItem,
    ResumeDivider
  },
  props: {
    title: {
      type: String
    },
    subTitle: {
      type: String
    },
    startYear: {
      type: Number
    },
    endYear: {
      type: Number
    },
    description: {
      type: String
    },
    portfolioItems: {
      type: Array
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.resume__portfolio-list {
  padding: 0;
  list-style: none;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.resume__portfolio-item {
  margin-bottom: 1.5rem;
}

.resume__item {
  position: relative;
  margin: 0;
  padding-left: 7.25rem;
}

.resume__date {
  position: absolute;
  left: 0;
  width: 6.25rem;
  margin: 0;
  span {
    font-size: 0.875rem;
    vertical-align: middle;
  }
}
</style>
