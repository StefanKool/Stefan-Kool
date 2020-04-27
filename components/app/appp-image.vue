<template>
  <lazy-load>
    <picture
      slot="content"
    >
      <source
        :srcset="`https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.webp 1x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.3.webp 1.3x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.5.webp 1.5x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.6.webp 1.6x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x2.webp 2x`"
        type="image/webp"
      >
      <source
        :srcset="`https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.jpg 1x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.3.jpg 1.3x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.5.jpg 1.5x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x1.6.jpg 1.6x,
                  https://static.stefankool.com/images/${fileName(image.src)}--h${height}-x2.jpg 2x`"
        type="image/jpg"
      >
      <img
        :width="width"
        :height="height"
      >
    </picture>
    <img
      slot="placeholder"
      src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      :width="width"
      :height="height"
      class="responsive-image__placeholder"
    />
  </lazy-load>
</template>

<script>
import LazyLoad from '../components/lazy-load.vue'

export default {
  name: 'responsive-image',
  components: { LazyLoad },
  props: {
    width: {
      type: Number,
      default: null
    },
    height: {
      type: Number,
      default: null
    },
    image: {
      type: Object,
      default: null
    }
  },
  methods: {
    fileName: function (fileName) {
      if (!fileName) return
      fileName = fileName.replace(/\.[^/.]+$/, '')
      return fileName
    }
  }
}
</script>

<style lang="scss">
img {
  vertical-align: middle;
}
picture {
  display: block;
}
</style>
