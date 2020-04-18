<template>
  <main>
    <template v-for="(item, index) in home.components">
      <agile-header
        v-if="item.component === 'agile-header'"
        :key="index"
      />
      <agile-expertise
        v-if="item.component === 'agile-expertise'"
        :key="index"
      />
      <agile-t-shape
        v-if="item.component === 'agile-t-shape'"
        :key="index"
      />
      <articles-list :posts="posts"
        v-if="item.component === 'articles-list'"
        :key="index"
      />
      <agile-lean-practitioner
        v-if="item.component === 'agile-lean-practitioner'"
        :key="index"
      />
      <agile-contact
        v-if="item.component === 'agile-contact'"
        :key="index"
      />
      <agile-reading
        v-if="item.component === 'agile-reading'"
        :key="index"
      />
      <app-divider
        v-if="item.component === 'app-divider'"
        :class="item.class"
        :key="index"
      />
    </template>
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
  name: 'home-page',
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
  computed: {
    home () {
      return require(`../static/data/en/layouts/default`)
    }
  },
  async asyncData({ params }) {
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
  head() {
    if (!this.ready) {
      return
    }

    return toHead(this.site.favicon)
  }
}
</script>
