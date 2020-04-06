<template>
  <div>
    <nuxt />
    <app-footer />
  </div>
</template>

<script>
import AppFooter from '@/components/app/app-footer.vue'

export default {
  name: 'default',
  components: {
    AppFooter
  }
}
</script>
