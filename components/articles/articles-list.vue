<template>
  <section class="comp comp-articles-list">
      <ul class="container container--max-8-col">
        <li
          v-for="post in posts"
          v-bind:key="post.slug"
        >
          <article>
            <!-- <datocms-image :data="post.coverImage.responsiveImage" /> -->
            <h4>
              {{ formatDate(post.publicationDate) }}
            </h4>
            <h3>
              <nuxt-link :to="`/article/${post.slug}`">
              {{ post.title }}
              </nuxt-link>
            </h3>
            <div v-html="post.excerpt" />
          </article>
        </li>
      </ul>
    </section>
</template>

<script>
import format from 'date-fns/format'
import parseISO from 'date-fns/parseISO'

export default {
  name: 'articles-list',
  props: {
    posts: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    formatDate(date) {
      return format(parseISO(date), 'PPP')
    }
  },
}
</script>

<style lang="scss">
.comp-articles-list {
  li {
    list-style: none;
  }
}
</style>


