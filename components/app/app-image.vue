<template>
  <img
    loading="lazy"
    :src="imgUrl"
    :width="imgWidth"
    :height="imgHeight"
    :alt="imgAlt"
  />
</template>

<script>
export default {
  name: 'app-image',
  props: {
    imgFileName: {
      type: String,
      required: true,
    },
    imgWidth: {
      type: Number,
    },
    imgHeight: {
      type: Number,
    },
    imgAlt: {
      type: String,
      default: '',
    }
  },
  computed: {
    imgUrl () {
      return require(`~/assets/img/${this.imgFileName}`) // need to compute and require for webpack to pickup the img
    }
  }
}
</script>
