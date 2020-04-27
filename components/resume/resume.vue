<template>
  <article class="comp-resume">
    <resume-header
      :header="resume.header"
    />
    <div class="container container--grid">
      <aside class="resume__aside">
        <div class="border__right resume--padding">
          <template v-for="(item, index) in resume.aside">
            <resume-online
              v-if="item.module === 'online'"
              :key="'online-' + index"
              :title="item.title"
              :subTitle="item.subTitle"
              :items="item.items"
            />
            <resume-references
              v-if="item.module === 'references'"
              :key="'references-' + index"
            />
            <resume-languages
              v-if="item.module === 'languages'"
              :key="'languages-' + index"
              :title="item.title"
              :subTitle="item.subTitle"
              :items="item.items"
            />
            <resume-aside-list
              v-if="item.module === 'aside-list'"
              :key="'aside-list-' + index"
              :title="item.title"
              :subTitle="item.subTitle"
              :items="item.items"
            />
            <resume-download
              v-if="item.module === 'download'"
              :key="'download-' + index"
            />
          </template>
        </div>
      </aside>
      <div class="resume__body">
        <div class="resume--padding">
          <template v-for="(item, index) in resume.body">
            <resume-profile
              v-if="item.module === 'profile'"
              :key="'profile-' + index"
              :title="item.title"
              :description="item.description"
            />
            <resume-section
              v-if="item.module === 'section'"
              :key="'section-' + index"
              :title="item.title"
              :resumeItems="item.items"
            />
            <resume-divider
              :key="'divider-' + index"
              class="resume--large-divider"
            />
          </template>
        </div>
      </div>
    </div>
    <footer class="print-footer"></footer>
  </article>
</template>

<script>
import ResumeHeader from '@/components/resume/modules/resume-header.vue'
import ResumeOnline from '@/components/resume/modules/resume-online.vue'
import ResumeReferences from '@/components/resume/modules/resume-references.vue'
import ResumeLanguages from '@/components/resume/modules/resume-languages.vue'
import ResumeAsideList from '@/components/resume/modules/resume-aside-list.vue'
import ResumeDownload from '@/components/resume/modules/resume-download.vue'
import ResumeProfile from '@/components/resume/modules/resume-profile.vue'
import ResumeSection from '@/components/resume/modules/resume-section.vue'
import ResumeItem from '@/components/resume/modules/resume-item.vue'
import ResumeDivider from '@/components/resume/modules/resume-divider.vue'

export default {
  layout: 'detail',
  name: 'resume',
  components: {
    ResumeHeader,
    ResumeOnline,
    ResumeReferences,
    ResumeLanguages,
    ResumeAsideList,
    ResumeDownload,
    ResumeProfile,
    ResumeSection,
    ResumeItem,
    ResumeDivider
  },
  props: {
    resume: {
      type: Object
    }
  }
}
</script>

<style lang="scss">
/* add utilities */
@import '~assets/scss/utilities.scss';

.comp-resume {
  margin-bottom: 2.5rem;

  section {
    *:first-child {
      margin-top: 0;
    }
  }
}

.resume__aside {
  grid-column: span 3;
  display: flex;
}

.resume__body {
  grid-column: span 9;
}

.resume--padding {
  margin: 1.25rem 0;
  padding: 1.25rem 2.5rem;
}

@media screen and (max-width: 839px) {
  .resume--padding {
    padding: 1.25rem;
  }
}

/*
** aside stuff
*/

.border__right {
  border-right: 1px solid #e7e8e1;
}

/*
**  print stuff
*/

.resume__print-spacer {
  display: none;
}

.print-footer {
  background-color: #192d40;
  display: none;
  position: fixed;
  width: 100%;
  bottom: 0;
  color: #ffffff;
}

.print-footer:after {
  counter-increment: page;
  content: counter(page);
}

.print-css {
  .resume__aside {
    width: 50mm !important;
  }
  .resume__body {
    width: 160mm !important;
  }

  .resume__grid-offset {
    margin: 0 !important;
  }

  .print--no-margin-right {
    margin-right: 0 !important;
  }

  .comp-resume {
    background-color: #ffffff;
    .container {
      width: 210mm;
      margin: 0;
      padding: 0;
      border: 0;
      float: none !important;
      color: black;
      background: #fff;
      box-shadow: none;
    }
  }

  body {
    background: #fff;
    font-size: 7pt;
  }

  .resume__divider,
  .resume__divider.resume--large-divider {
    page-break-after: avoid;
    margin: 6.5mm 0;
  }

  h1 + p,
  h2 + p,
  h3 + p {
    page-break-before: avoid;
  }

  p,
  li {
    font-size: 7pt;
    page-break-inside: avoid;
  }

  ul,
  ol {
    line-height: 1.6;
    letter-spacing: 0;
    margin-top: 0;
  }

  h1 {
    font-size: 32pt;
  }

  h4 {
    font-size: 12pt;
  }

  h5 {
    font-size: 10pt;
  }

  h6,
  p {
    line-height: 1.72;
  }

  p {
    margin-bottom: 6pt;
  }

  a[href]:after {
    font-size: 4pt;
  }

  h2,
  h3 {
    margin: 12pt 0;
  }

  h4 {
    margin: 14pt 0 6pt;
    line-height: 1.2;
  }

  .margin-bottom-40px {
    margin-bottom: 6pt;
  }

  .resume__contact-details {
    font-size: 7pt;
    padding: 4mm 0;
  }

  .resume__contact-details .margin-bottom-1sp {
    margin-bottom: 0;
  }

  .resume__divider {
    margin: 4mm 0;
  }

  .resume--padding {
    padding: 6.5mm;
  }

  .margin-bottom-1sp {
    margin-bottom: 2mm;
  }

  .margin-bottom-5sp {
    margin-bottom: 6.5mm;
  }

  .padding-top-2p {
    padding-top: 0;
    margin-top: 0;
  }

  .no-padding-bottom {
    padding-bottom: 0;
  }

  .resume__header svg {
    fill: #fff;
  }

  .resume__header img {
    width: 39.5mm;
  }

  .resume__item {
    padding-left: 19mm;
  }

  .resume__date {
    font-size: 7pt;
    width: 16mm;
    top: 0;
  }

  .resume__progress-bar {
    height: 2mm;
    left: 8mm;
    margin: 2mm 0;
  }

  .resume__progress-bar-indication {
    height: 2mm;
  }

  .resume__certification-panel img {
    width: 10mm;
    height: 17mm;
    margin: 2mm;
  }

  .resume__reference-line {
    padding: 0 3mm;
  }

  .reference-line--name {
    height: 3mm;
  }

  .reference-line--title {
    height: 3mm;
  }

  .resume__reference-person {
    padding-left: 10mm;
  }

  .resume__reference-avatar {
    width: 8mm;
    height: 8mm;
    line-height: 8mm;
  }

  .resume__print-spacer {
    display: block;
    height: 10mm;
  }

  .mdl-grid--no-spacing > .mdl-cell--9-col.resume--motivation,
  .mdl-grid--no-spacing > .mdl-cell--9-col-desktop.resume--motivation {
    width: 185mm;
  }

  .resume--motivation p,
  .resume--motivation li {
    font-size: 10pt;
    line-height: 1.4;
    margin-bottom: 10pt;
  }

  .resume__icon-panel {
    width: 6mm;
    height: 6mm;
    line-height: 6mm;
    margin-right: 0;
  }

  .resume__header {
    background-color: #192d40 !important;
    color: #fff !important;
  }

  .resume__download {
    display: none;
  }

  .resume__header *,
  .resume__header *:before,
  .resume__header *:after {
    color: #fff !important;
  }

  .resume__item {
    page-break-inside: avoid;
  }
/*
  .print-footer {
    display: block !important;
  }
 */

  /*
* Print page css
*/

  @page {
    size: A4 portrait;
    margin: 13mm 0;
  }

  @page :first {
    margin-top: 0;
    margin-bottom: 10mm;
  }
}
</style>
