<template>
  <section class="margin-bottom-5sp">
    <h5 class="type--bold-sc no-margin-top">Languages</h5>
    <div class="column-row">
      <app-icon class="resume__icon-panel app-icon--flag" :iconId="'flag-nl'" />
      <div class="resume__progress-bar">
        <div
          class="resume__progress-bar-indication"
          style="width: 100%;"
        ></div>
      </div>
    </div>
    <div class="column-row">
      <app-icon class="resume__icon-panel app-icon--flag" :iconId="'flag-gb'" />
      <div class="resume__progress-bar">
        <div
          class="resume__progress-bar-indication"
          style="width: 80%;"
        ></div>
      </div>
    </div>
    <div class="column-row">
      <app-icon class="resume__icon-panel app-icon--flag" :iconId="'flag-de'" />
      <div class="resume__progress-bar">
        <div
          class="resume__progress-bar-indication"
          style="width: 40%;"
        ></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'resume-languages'
}
</script>

<style lang="scss">
/* add utilities */
@import "~assets/scss/utilities.scss";

.icon-panel--flag {
  display: block;
}

.resume__progress-bar {
  height: 0.6rem;
  position: absolute;
  left: 2.5rem;
  right: 0;
  top: 0;
  margin: 0.7rem 0;
  float: right;
  background-color: #f3f3f3;
  border-radius: 4px;
  overflow: hidden;
}

.resume__progress-bar-indication {
  background-color: #192d40;
  height: 0.6rem;
  width: 0%;
  border-radius: 4px;
}
</style>


