<template>
  <main>
    <agile-header />
    <app-divider />
    <agile-expertise />
    <app-divider class="app-divider--reverse app-divider--alternate" />
    <agile-t-shape />
    <app-divider class="app-divider--alternate" />
    <articles-list :posts="posts" />
    <agile-lean-practitioner />
    <agile-contact />
    <app-divider class="app-divider--reverse" />
    <agile-reading />
  </main>
</template>

<script>
import { request, gql, imageFields, seoMetaTagsFields } from '~/lib/datocms'
import { toHead } from 'vue-datocms'

import AgileHeader from '@/components/agile/agile-header.vue'
import AppDivider from '@/components/app/app-divider.vue'
import AgileExpertise from '@/components/agile/agile-expertise.vue'
import AgileTShape from '@/components/agile/agile-t-shape.vue'
import ArticlesList from '@/components/articles/articles-list.vue'
import AgileLeanPractitioner from '@/components/agile/agile-lean-practitioner.vue'
import AgileContact from '@/components/agile/agile-contact.vue'
import AgileReading from '@/components/agile/agile-reading.vue'

export default {
  name: 'home',
  components: {
    AgileHeader,
    AppDivider,
    AgileExpertise,
    AgileTShape,
    ArticlesList,
    AgileLeanPractitioner,
    AgileContact,
    AgileReading
  },
  async asyncData ({ params }) {
    const data = await request({
      query: gql`
        {
          site: _site {
            favicon: faviconMetaTags {
              ...seoMetaTagsFields
            }
          }

          posts: allPosts(first: 10, orderBy: _firstPublishedAt_DESC) {
            id
            title
            slug
            publicationDate: _firstPublishedAt
            excerpt
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
      `
    })

    return { ready: !!data, ...data }
  },
  head () {
    if (!this.ready) {
      return
    }

    return toHead(this.site.favicon)
  }
}
</script>
