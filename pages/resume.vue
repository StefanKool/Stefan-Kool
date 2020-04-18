<template>
  <main>
    <resume v-bind:resume="resume" />
  </main>
</template>

<script>
import Resume from '@/components/resume/resume.vue'

export default {
  layout: 'detail',
  name: 'resume-page',
  components: {
    Resume
  },
  computed: {
    resume () {
      return require(`../static/data/en/layouts/default/resume`)
    }
  }
}
</script>
