<template>
  <section class="comp comp-article">
    <article class="container container--grid">
      <figure>
        <datocms-image class="image" :data="post.coverImage.responsiveImage" />
        <figcaption>This foto is by</figcaption>
      </figure>
      <h6>
        {{ formatDate(post.publicationDate) }}
      </h6>
      <h2 class="type--bold-sc">
        {{ post.title }}
      </h2>
      <div v-html="htmlBody" />
    </article>
  </section>
</template>

<script>
import { request, gql, imageFields, seoMetaTagsFields } from '~/lib/datocms'
import { toHead } from 'vue-datocms'
import renderMarkedContent from '~/lib/render-marked'
import format from 'date-fns/format'
import parseISO from 'date-fns/parseISO'

export default {
  layout: 'detail',
  name: 'article-detail-page',
  async asyncData({ params }) {
    const data = await request({
      query: gql`
        query BlogPostQuery($slug: String!) {
          site: _site {
            favicon: faviconMetaTags {
              ...seoMetaTagsFields
            }
          }

          post(filter: { slug: { eq: $slug } }) {
            seo: _seoMetaTags {
              ...seoMetaTagsFields
            }
            id
            title
            slug
            publicationDate: _firstPublishedAt
            content
            coverImage {
              responsiveImage(imgixParams: { fit: crop, ar: "16:9", w: 860 }) {
                ...imageFields
              }
            }
            author {
              name
              picture {
                responsiveImage(imgixParams: { fit: crop, ar: "1:1", w: 40 }) {
                  ...imageFields
                }
              }
            }
          }
        }

        ${imageFields}
        ${seoMetaTagsFields}
      `,
      variables: {
        slug: params.id
      }
    })

    return { ready: !!data, ...data }
  },
  methods: {
    formatDate(date) {
      return format(parseISO(date), 'PPP')
    }
  },
  computed: {
    htmlBody () {
      return renderMarkedContent(this.post.content)
    }
  },
  head() {
    if (!this.ready) {
      return
    }

    return toHead(this.post.seo, this.site.favicon)
  }
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.comp-article {
  .container--grid {
    grid-row-gap: 0;
    grid-auto-rows: max-content;
    & * {
      max-width: 38rem;
      grid-column-end: span 4;
      @include media(tablet-and-larger) {
        grid-column-end: span 6;
        grid-column-start: 2;
      }
      @include media(desktop-and-larger) {
        grid-column-end: span 11;
        grid-column-start: 4;
      }
    }
  }
}
</style>
