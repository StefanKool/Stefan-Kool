<template>
  <div>
    <app-nav />
    <nuxt />
    <app-footer />
  </div>
</template>

<script>
import AppNav from '@/components/app/app-nav.vue'
import AppFooter from '@/components/app/app-footer.vue'

export default {
  name: 'detail',
  components: {
    AppNav,
    AppFooter
  }
}
</script>
