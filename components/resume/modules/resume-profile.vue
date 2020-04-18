<template>
  <section class="mod-resume-profile">
    <h2
      class="h3 type--bold-sc"
      v-if="title"
    >
      {{ title }}
    </h2>
    <p
      v-if="description"
    >
      {{ description }}
    </p>
  </section>
</template>

<script>
export default {
  name: 'resume-profile',
  props: {
    title: {
      type: String
    },
    description: {
      type: String
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.mod-resume-profile {
  p {
    margin-bottom: 2.5rem;
  }
}

</style>


